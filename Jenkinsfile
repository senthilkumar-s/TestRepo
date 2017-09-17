node {
    // Use the shell to create the file 'script.groovy' 
    sh '''echo '
    def hello(name) {
        echo "Hello again ${name} from forked script" 
    }
    return this
    ' > script.groovy'''
    def script = load 'script.groovy'
    script.hello('Roy')
}
def buildFeatureBranch() {
    echo "Feature branch"
}

def buildDevelopBranch() {
    echo "Develop branch"
}

def buildReleaseBranch() {
    echo "Release branch"
}

def buildMasterBranch() {
    echo "Master branch"
}

def buildHotfixBranch() {
    echo "Hotfix branch"
}

node {
    checkout scm
    
    def name = env.BRANCH_NAME
    if (name.startsWith('feature/')) {
        buildFeatureBranch()
    } else if (name == 'develop') {
        buildDevelopBranch()
    } else if (name.startsWith('release/')) {
        buildReleaseBranch()
    } else if (name == 'master') {
         buildMasterBranch()
    } else if (name.startsWith('hotfix/')) {
        buildHotfixBranch()
    } else {
        error "Don't know what to do with this branch: ${name}"
    }
}
