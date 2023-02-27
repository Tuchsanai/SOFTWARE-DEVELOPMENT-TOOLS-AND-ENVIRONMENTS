# Parameters

A very rich feature of jenkins is that jobs can be parameterized. In pipelines, we have a directive named as parameters.The values for these user-specified parameters are made available to Pipeline steps via the params object.

```
pipeline {
    agent any
    parameters {
        string(name: 'NAME', defaultValue: 'Tuchsanai', description: 'Enter your name')
        choice(name: 'CITY', choices: ['Bangkok',Bebbanburg', 'Mercia', 'East Anglia'], description: 'Choose your city')
    }
    stages {
        stage('Example') {
            steps {
                echo "Hello ${params.NAME} of ${params.CITY}"
            }
        }
    }
}
```
To see complete list of parameters, you may refer https://www.jenkins.io/doc/book/pipeline/syntax/#parameters

