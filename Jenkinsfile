node {
    // Use the shell to create the file 'script.groovy' 
    sh '''echo '
    def hello(name) {
        echo "Hello again ${name} from master script" 
    }
    return this
    ' > script.groovy'''
    def script = load 'script.groovy'
    script.hello('Roy')
}
