# Slaves

```
pipeline {
    agent any
    parameters {
        string(name: 'NAME', defaultValue: 'Tuchsanai', description: 'Enter your name')
        choice(name: 'CITY', choices: ['Bangkok','Bebbanburg', 'Mercia', 'East Anglia'], description: 'Choose your city')
    }
    stages {
        stage('Example') {
            steps {
                echo "Hello from Slave ${params.NAME} of ${params.CITY}"
                
            }
        }
    }
}
```

# Master




To see complete list of parameters, you may refer https://www.jenkins.io/doc/book/pipeline/syntax/#parameters

