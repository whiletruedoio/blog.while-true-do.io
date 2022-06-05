<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

[![Cirrus CI - Base Branch Build Status](https://img.shields.io/cirrus/github/whiletruedoio/blog.while-true-do.io?logo=Cirrus-ci)](https://cirrus-ci.com/github/whiletruedoio/blog.while-true-do.io)
[![CodeFactor](https://www.codefactor.io/repository/github/whiletruedoio/blog.while-true-do.io/badge)](https://www.codefactor.io/repository/github/whiletruedoio/blog.while-true-do.io)
[![GitHub Tag (latest SemVer)](https://img.shields.io/github/v/tag/whiletruedoio/blog.while-true-do.io?logo=GitHub&label=Release&sort=semver)](https://github.com/whiletruedoio/blog.while-true-do.io/releases)
[![GitHub issues](https://img.shields.io/github/issues/whiletruedoio/blog.while-true-do.io)](https://github.com/whiletruedoio/blog.while-true-do.io/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/whiletruedoio/blog.while-true-do.io)](https://github.com/whiletruedoio/blog.while-true-do.io/pulls)
[![GitHub license](https://img.shields.io/github/license/whiletruedoio/blog.while-true-do.io)](https://github.com/whiletruedoio/blog.while-true-do.io/blob/main/LICENSE)

# blog.while-true-do.io

 Code for the blogging service of [while-true-do.io.](https://while-true-do.io/).

## Motivation

As a community project, we want to inform our users and publish knowledge. This
can be done with a platform that allows contributors to publish new articles on
a regular basis.

## Description

The repository holds the deployment data for
[blog.while-true-do.io](https://while-true-do.io/). The blog engine is based
on the popular and simple [Ghost](https://ghost.org/) blogging platform.

In addition, we will track new ideas and article progress in the
[GitHub issues](https://github.com/whiletruedoio/blog.while-true-do.io/issues).

## Architecture

You can find a small architectural diagram of the blog engine in the
[docs](./docs) directory.

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

The deployment is done on Kubernetes. Therefore, you will need a Kubernetes
instance running to apply the deployment. As a reference, you can have a look
at
[kube.while-true-do.io](https://github.com/whiletruedoio/kube.while-true-do.io).

For development purposes, you can also use
[Minikube](https://minikube.sigs.k8s.io/docs/)
or plain [k3s](https://k3s.io).

### Install

The installation of the deployment is done with
[kustomize](https://kustomize.io). Kustomize is baked into
[kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/).

For now, we are offering 3 different environments:

#### Home

The home environment is the default environment. It can be used for your
personal home server, development or small environments.

```bash
# Deploy to the home environment
$ kubectl apply -k kubernetes/overlays/home/
```

This will create:

- a namespace "blog-home-while-true-do-io"
- an ingress "blog.home.while-true-do.io"
- the necessary services, deployments, configMap and persistent volumes

#### Test

The test environment is used for testing purposes. It is used in our testing
area to learn about new features and try out new ideas.

```bash
# Deploy to the test environment
$ kubectl apply -k kubernetes/overlays/test/
```

This will create:

- a namespace "blog-test-while-true-do-io"
- an ingress "blog.test.while-true-do.io"
- the necessary services, deployments, configMap and persistent volumes

#### Prod

The production environment is used for the deployment of the blog. For now, it
does not differ from other deployments, but is intended to facilitate certain
scaling and HA features in the future.

```bash
# Deploy to the prod environment
$ kubectl apply -k kubernetes/overlays/prod/
```

This will create:

- a namespace "blog-prod-while-true-do-io"
- an ingress "blog.while-true-do.io"
- the necessary services, deployments, configMap and persistent volumes

### Documentation

The deployment is based on the famous [Ghost](https://ghost.org/) blogging
engine which is documented in the [Ghost](https://ghost.org/resources/)
documentation.

The software is open source and can be found on
[GitHub](https://github.com/TryGhost/Ghost).

## Contribute

Thank you so much for considering to contribute! We are happy, when someone is
joining the hard work. Please have a look at the
[Contributor Conventions](https://github.com/whiletruedoio/.github/blob/main/docs/CONTRIBUTING.md)
beforehand.

### Issues

Issues and Pull Requests are handled on a regular basis. Please be aware, that
we may reach out to you, ask you to provide additional resources or want to
discuss the issue a little, before planning it.

- [Bugs and Feature Requests](https://github.com/whiletruedoio/blog.while-true-do.io/issues)
- [Pull Requests](https://github.com/whiletruedoio/blog.while-true-do.io/pulls)

### Develop

In case you want to customize the deployment or help developing, you should copy
one of the overlays and inspect each of the files. You need to adjust at least:

- the namespace.yml
- the ingress.yml
- the blog-web.env

You should also make yourself comfortable with the use of
[MiniKube](https://minikube.sigs.k8s.io/docs/) and
[Kustomize](https://github.com/kubernetes-sigs/kustomize).

### Changelog

We are maintaining a [changelog](CHANGELOG.md) for repositories. Normally, the
developers will update the changelog, according to
[keepachangelog.com](https://keepachangelog.com/).

### Test

To ensure a high quality and functionality, we want to carefully test our
software. The provided code is automatically tested as described in the
[.cirrus.yml](.cirrus.yml).

## License

Except otherwise noted, all work is [licensed](LICENSE) under a
[BSD-3-Clause License](https://opensource.org/licenses/BSD-3-Clause).

<!-- TODO: License

Adapt the LICENSE to your needs.
-->

## Contact

Please feel free to reach out to us and the community. We also recommend to read
and understand the
[Code of Conduct](https://github.com/whiletruedoio/.github/blob/main/docs/CODE_OF_CONDUCT.md)
beforehand.

- Site: <https://while-true-do.io>
- Blog: <https://blog.while-true-do.io>
- Code: <https://github.com/whiletruedoio>
- Chat: [libera.chat #whiletruedoio](https://web.libera.chat/gamja/#whiletruedo)
- Mail: [hello@while-true-do.io](mailto:hello@while-true-do.io)
