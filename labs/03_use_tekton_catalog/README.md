# Use Tekton CD Catalog

This folder holds the files for the lab: _Use Tekton CD Catalog_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

Use this command to install the git-clone task from Tekton Hub:
```bash
tkn hub install task git-clone --version 0.8
```

Note: If the above command returns a error due to Tekton Version mismatch, please run the below command to fix this.
```bash
kubectl apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.9/git-clone.yaml
```

Apply the new task definition to the cluster:
```bash
kubectl apply -f pvc.yaml
```

Apply the pipeline to your cluster:
```bash
kubectl apply -f pipeline.yaml
```

You can now use the Tekton CLI (tkn) to create a PipelineRun to run the pipeline:
```bash
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode.git" \
    -p branch="main" \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```