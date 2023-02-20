# Pipeline using Pipeline script

Dashboard > New Item > Pipeline

<p align="left">
<img src="/images/create_pipeline.png" width="60%" height="60%">
</p>


Definition = Pipeline script

<p align="left">
<img src="/images/first_pipeline_script.png" width="60%" height="60%">
</p>


Enter script
    
    

Linux
```
   pipeline {
   agent any
    stages {
        stage('build') {
            steps {
                
                sh 'echo welcome to first pipeline'
                sh 'python3 -version'
            }
        }
    }
}
```

Output:

<p align="left">
<img src="/images/first_pipeline_script_output.png" width="60%" height="60%">
</p>
