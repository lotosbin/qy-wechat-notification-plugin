# use in Jenkinsfile
替换webhook_url为企业微信机器人的地址
```groovy
pipeline {
    stages {
        stages("xxx") {
            steps {
                qyWechatNotification(failNotify: false, webhookUrl: 'webhook_url')
            }
        }
    }
    post {
        unstable {
            qyWechatNotification(failNotify: false, webhookUrl: 'webhook_url')
        }

        success {
            qyWechatNotification(failNotify: false, webhookUrl: 'webhook_url')
        }

        failure {
            qyWechatNotification(failNotify: true, webhookUrl: 'webhook_url')
        }
    }
}
```
