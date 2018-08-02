import com.tikal.jenkins.plugins.multijob.*
import hudson.*
import hudson.model.*
import hudson.plugins.git.*
import hudson.slaves.*
import hudson.tasks.*

def ln = System.getProperty('line.separator')
println "---------------Groovy Changelog script Started---------------$ln"

def lastSuccesfulBuild = build.previousNotFailedBuild
def failed = build.result != hudson.model.Result.SUCCESS

println "Last Succesful Build: ${lastSuccesfulBuild}"
println "Current Build Result, is failed?: ${failed}"


def currResult = build.result
def prevResult = build.previousBuild?.result ?: null

def consecutiveSuccess = currResult == hudson.model.Result.SUCCESS && prevResult == hudson.model.Result.SUCCESS

def builds = []
def changes = []
def count = 0



if (consecutiveSuccess) {
    println "Last Build was sucessful, getting latest changes$ln"

    builds << build
    def changeItems = build.changeSet.items
    println "Change Items: ${changeItems}$ln"

    count += changeItems.length
    changes += changeItems as List
} else {
    println "Last Build was not sucessful, getting changes from all failed build as well$ln"

    println "BUILD: $build$ln"

    println "Hudson version: $build.hudsonVersion$ln"

    println "Change set: $build.changeSet$ln"

    println "Change set items: $build.changeSet.items$ln"

    while (lastSuccesfulBuild) {
        builds << lastSuccesfulBuild
        def changeSet = lastSuccesfulBuild.changeSet
        if (!changeSet.emptySet) {
            def changeItems = lastSuccesfulBuild.changeSet.items
            count += changeItems.length
            changes += changeItems as List
        }
        lastSuccesfulBuild = lastSuccesfulBuild.nextBuild
    }
}

def file = new File(build.getEnvVars()["WORKSPACE"] + '\\changelog')
file.delete()
file = new File(build.getEnvVars()["WORKSPACE"] + '\\changelog')

if (count ==0){
    file << "No changes.$ln"
}

changes.each { item ->
    println "item: $item$ln"
    println "author: $item.authorName$ln"
    println "msg: $item.msg$ln"
    println "id: $item.id$ln"
    println "revision: $item.revision$ln"
    println "comment: $item.comment$ln"
    println "commentAnnotated: $item.commentAnnotated$ln"
    println "affectedFiles: $item.affectedFiles$ln"
    println "affectedPaths: $item.affectedPaths$ln"
    println "commitId: $item.commitId$ln"
    println "timestamp: $item.timestamp$ln"
    println "date: $item.date$ln"

    file << "Commit ID: $item.id, by $item.author on $item.date, timestamp: $item.timestamp$ln"
    file << "$item.comment$ln"

    item.affectedFiles.each { cl -> 
        println "editType: $cl.editType.description$ln"
        println "changeSet: $cl.changeSet$ln"
        println "path: $cl.path$ln"
        println "src: $cl.src$ln"
        println "dst: $cl.dst$ln"

        file << "$cl.editType.description: $cl.path$ln"
    }
    file << "$ln"
}

println "---------------Groovy Changelog script Finished---------------$ln"
