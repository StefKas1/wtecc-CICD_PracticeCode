# Adding GitHub Triggers

This folder holds the files for the lab: _Adding GitHub Triggers_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.



Once you have cloned the repository, change to the labs directory:
```bash
cd wtecc-CICD_PracticeCode/labs/02_add_git_trigger/
```

Apply task and pipeline:
```bash
kubectl apply -f tasks.yaml
kubectl apply -f pipeline.yaml
```

Check that the tasks were created:
```bash
tkn task ls
```

Check that the pipeline was created:
```bash
tkn pipeline ls
```

Apply the EventListener resource to the cluster:
```bash
kubectl apply -f eventlistener.yaml
```

Check that it was created correctly:
```bash
tkn eventlistener ls
```

Apply the new TriggerBinding definition to the cluster:
```bash
kubectl apply -f triggerbinding.yaml
```

Apply the new TriggerTemplate definition to the cluster:
```bash
kubectl apply -f triggertemplate.yaml
```