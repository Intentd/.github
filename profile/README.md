## Intentd

Open source for Kubernetes operators and the people who run them. Each project stands on its own; together they cover an operator's life: what it does, how its objects are built, how its schemas change, and how it is tested.

| Project | What it is | Version |
| --- | --- | --- |
| [**Inrun**](https://github.com/intentd/inrun) | A runtime that separates reconciliation behaviour from the machinery that runs it. Bring an intent and the decision logic; Inrun owns the informers, queues, retries, status and cleanup. | [![Inrun](https://img.shields.io/github/v/tag/intentd/inrun?label=)](https://github.com/intentd/inrun/tags) |
| [**KEL**](https://github.com/intentd/kel) | The Kubernetes Expression Library: functions that know Kubernetes, for Go templates and CEL. Health verdicts, rollouts, conditions, crash loops. | [![KEL](https://img.shields.io/github/v/tag/intentd/kel?label=)](https://github.com/intentd/kel/tags) |
| [**kubewright**](https://github.com/intentd/kubewright) | The child-resource code every operator writes, written once: idempotent verbs to build, apply and owner-safely delete, with presets for the settings every team repeats. | [![kubewright](https://img.shields.io/github/v/tag/intentd/kubewright?label=)](https://github.com/intentd/kubewright/tags) |
| [**KOME**](https://github.com/intentd/kome) | The Kubernetes Object Migration Engine: Alembic for Kubernetes objects. Move stored custom resources between schemas with up, down and clean, rehearsed first. | [![KOME](https://img.shields.io/github/v/tag/intentd/kome?label=)](https://github.com/intentd/kome/tags) |
| [**jig**](https://github.com/intentd/jig) | Declarative Kubernetes tests that own their environment: the cluster, the images, the steps and the checks in one file, on kind or an existing cluster, with a report every time. | [![jig](https://img.shields.io/github/v/tag/intentd/jig?label=)](https://github.com/intentd/jig/tags) |
| [**tools**](https://github.com/intentd/tools) | The shared building blocks: Kubernetes client and fake, conditions, the resolver for templates and CEL, assertions, cluster helpers. | |

### How they fit

Inrun builds on the others: its templates speak KEL, its children are written with kubewright, its migrations run through KOME, and its end-to-end tests run through jig. None of them depends on Inrun, so each can be used without it.

None installs a CRD of its own. Inrun, KOME and jig each work from a file you keep in your repository: a Blueprint, a `kome.yaml`, a `jig.yaml`. KOME's record lives as annotations on your own objects, and KEL, kubewright and tools are Go libraries. Stop using any of them and there is nothing of theirs left in the cluster to migrate away from.

All are written in Go.
