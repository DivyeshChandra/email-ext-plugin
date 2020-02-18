// this uses the buildPlugin step from
// The jenkins-infra/pipeline-library repo

def recentLTS = "2.164.1"

buildPlugin(
    forceAci: true, // this uses Azure Container Instances for the build
    failFast: false,
    configurations: [// Intentionally test configurations which have detected the most problems
        // Linux - Java 8 with plugin specified minimum Jenkins version
        // Windows - Java 8 with recent LTS
        // Linux - Java 11 with recent LTS
        [ platform: "linux", jdk: "8", jenkins: null ],
        // [ platform: "windows", jdk: "8", jenkins: null ],
        // [ platform: "linux", jdk: "8", jenkins: recentLTS, javaLevel: "8" ],
        [ platform: "windows", jdk: "8", jenkins: recentLTS, javaLevel: "8" ],
        [ platform: "linux", jdk: "11", jenkins: recentLTS, javaLevel: "8" ],
        [ platform: "windows", jdk: "11", jenkins: recentLTS, javaLevel: "8" ]
    ]
)
