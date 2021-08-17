# Orchestrating Spark pipeline using Argo Workflow

This repository serves as a rudimentary and simple example for 
[Apache Spark](https://spark.apache.org/) pipeline using 
[Argo Workflow](https://argoproj.github.io/workflows).

## Structure

```bash
├── .gitignore                      # .gitignore taken from gitignore.io
├── README.md                       # current file being read
├── argo                            # argo workflow folder
│   └── hello_world.yaml            # hello-world argo pipeline
└── spark                           # spark code folder
    ├── Dockerfile                  # Dockerfile to build and push JAR images
    ├── build.sbt                   # SBT build conf                 
    ├── project
    │   ├── build.properties        # SBT build properties
    │   ├── plugins.sbt             # SBT plugins
    ├── src
    │   └── main
    │       └── scala
    │           └── Main.scala      # main scala code defining code logic
```

## Usage

Step 1: edit your code and make needed changes

Step 2: create new docker image for edited code
```
cd spark
docker build -t ghcr.io/hrmnjt/argo-orchestrated-spark:latest .
```

Step 3: push the new image to docker repository
```
docker push ghcr.io/hrmnjt/argo-orchestrated-spark:latest
```

Step 4: run Argo Workflow `hello-world-from-spark` to find the latest changes
as per the code changes


## TODO

- [ ] Add real Spark code example
- [ ] Add workflow automation
- [ ] Local environment setup
- [ ] Screenshots to showcase process for learners
