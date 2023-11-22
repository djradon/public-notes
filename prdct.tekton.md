---
id: rsqds8jgt1igv9c2hr5bp0j
title: Tekton
desc: 'Cloud Native CI/CD'
updated: 1700694176492
created: 1689742141160
---

- [[t.cs.sd.architecture.orchestration]] vs [[t.cs.sd.architecture.choreography]]

## [[c.component]]

-   **Pipeline:** Pipeline defines a set of Kubernetes [Custom Resources](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) that act as building blocks you use to assemble your CI/CD pipelines.
-   **Triggers:** Triggers is a Kubernetes Custom Resource that allows you to create pipelines based on information extracted from event payloads. For example, you can trigger the instantiation and execution of a pipeline every time a merge request gets opened against a Git repository.
-   **CLI:** CLI provides a command-line interface called `tkn` that allows you to interact with Tekton from your terminal.
-   **Dashboard:** Dashboard is a web-based graphical interface for Tekton pipelines that displays information about the execution of your pipelines.
-   **Catalog:** Catalog is a repository of high-quality, community-contributed Tekton building blocks (tasks, pipelines, and so on) ready for use in your own pipelines.
-   **Hub:** Hub is a web-based graphical interface for accessing the Tekton catalog.
-   **Operator:** Operator is a Kubernetes [Operator pattern](https://operatorhub.io/what-is-an-operator) that allows you to install, update, upgrade, and remove Tekton projects on a Kubernetes cluster.
-   **Chains:** Chains is a Kubernetes Custom Resource Definition (CRD) controller that allows you to manage your supply chain security in Tekton. It is currently a work-in-progress.
-   **Results:** Results aims to help users logically group CI/CD workload history and separate out long-term result storage away from the pipeline controller.

## [[c.term]]

  -   **Step:** A step is the most basic entity in a CI/CD workflow, such as running some unit tests for a Python web app or compiling a Java program. Tekton performs each step with a provided container image.
-   **Task:** A task is a collection of steps in a specific order. Tekton runs a task in the form of a [Kubernetes pod](https://kubebyexample.com/en/concept/pods), where each step becomes a running container in the pod.
-   **Pipelines:** A pipeline is a collection of tasks in a specific order. Tekton collects all tasks, connects them in a directed acyclic graph (DAG), and executes the graph in sequence. In other words, it creates a number of Kubernetes pods and ensures that each pod completes running successfully as desired.  
    
    ![Tekton pipelines](https://opensource.com/sites/default/files/uploads/tekton-pipelines.png "Tekton pipelines")
    
    
-   **PipelineRun:** A PipelineRun, as its name implies, is a specific execution of a pipeline.
-   **TaskRun:** A TaskRun is a specific execution of a task. TaskRuns are also available when you choose to run a task outside a pipeline, with which you may view the specifics of each step execution in a task.

## Resources

- https://www.redhat.com/en/blog/tekton-vs-jenkins-whats-better-cicd-pipelines-red-hat-openshift
  - "the notion of formal dev, test and UAT type environments is largely an old-world concept."

## Comparison

- https://platform9.com/blog/argo-cd-vs-tekton-vs-jenkins-x-finding-the-right-gitops-tooling/