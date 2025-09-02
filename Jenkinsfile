@Library('react-sonar-scan') _

node {
    reactSonarScan(
        projectKey: 'OT-MICROSERVICES-frontend',
        projectName: 'OT-MICROSERVICES Frontend',
        // No need to specify repoUrl when using SCM checkout
        sonarUrl: 'http://192.168.1.3:9000',
        notifyEmail: 'ashutosh.devpro@gmail.com',
        enableQualityGate: true
    )
}
