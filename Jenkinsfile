// Run on an agent where we want to use Go
node {
    // Ensure the desired Go version is installed
    def root = "/usr/local/go/bin/go"

    // Export environment variables pointing to the directory where Go was installed
    withEnv(["GOROOT=${root}", "PATH+GO=${root}/bin"]) {
    
        stage 'Checkout'
        checkout git: 'https://github.com/zahrul100/sample-go-jenkins.git'
        
        stage 'preTest'
        sh '${root} version'
        
        stage 'Test'
        sh '${root} test ./... -cover'
        
        stage 'Build'
        sh '${root} build ./...'
            
    }
}