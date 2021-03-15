# LAB: Hello world with variants

Tis article is based on: https://github.com/kubernetes-sigs/kustomize/tree/master/examples/helloWorld



**STEPS:**

1. Clone an existing configuration as a **base**.

   > A *base* is a [kustomization](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#kustomization) referred to by some other [kustomization](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#kustomization).
   >
   > Any kustomization, including an [overlay](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#overlay), can be a base to another kustomization.
   >
   > A base has no knowledge of the overlays that refer to it.
   >
   > For simple [gitops](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#gitops) management, a base configuration could be the *sole content of a git repository dedicated to that purpose*. Same with [overlays](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#overlay). Changes in a repo could generate a build, test and deploy cycle.

2. Customize it.

3. Create two different **overlays** (staging and production) from the customized base.

   > An *overlay* is a kustomization that depends on another kustomization.
   >
   > The [kustomizations](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#kustomization) an overlay refers to (via file path, URI or other method) are called [bases](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#base).
   >
   > An overlay is unusable without its bases.
   >
   > An overlay may act as a base to another overlay.
   >
   > Overlays make the most sense when there is *more than one*, because they create different [variants](https://kubectl.docs.kubernetes.io/references/kustomize/glossary/#variant) of a common base - e.g. *development*, *QA*, *staging* and *production* environment variants.
   >
   > These variants use the same overall resources, and vary in relatively simple ways, e.g. the number of replicas in a deployment, the CPU to a particular pod, the data source used in a ConfigMap, etc.

4. Run Kustomize and kubectl to deploy staging and production.



