---
title: "Stop Typing kubectl 800 Times a Day"
date: 2025-04-13 10:30:00 -0400
categories: [Kubernetes]
tags: [kubernetes, kubectl, productivity, developer-experience]
---

If you work with Kubernetes daily and you're still typing `kubectl` in full, here's five minutes of setup that will save you hours.

## The Alias

Add this to your `.bashrc` or `.zshrc`:

```bash
alias k='kubectl'
```

Now `kubectl get pods` becomes `k get pods`. Your fingers will thank you immediately.

## The Autocomplete

This is the part people skip. Don't skip it.

```bash
# Bash
source <(kubectl completion bash)
complete -o default -F __start_kubectl k

# Zsh
source <(kubectl completion zsh)
compdef k=kubectl
```

Now you can type `k get po<TAB>` and it completes to `k get pods`. It also completes resource names, namespaces, and context names. This is the real productivity gain.

## The Namespace Default

Tired of typing `-n monitoring` on every command?

```bash
k config set-context --current --namespace=monitoring
```

Now every command runs against that namespace until you change it. When you're done:

```bash
k config set-context --current --namespace=default
```

Or use `kubens` from the `kubectx` project if you switch namespaces frequently. It's a single command with fuzzy search.

## The Context Switcher

If you work with multiple clusters:

```bash
# Install kubectx
brew install kubectx  # or your package manager

# Switch clusters
kubectx my-dev-cluster
kubectx my-prod-cluster
```

No more `k config use-context arn:aws:eks:us-east-1:123456789:cluster/my-incredibly-long-cluster-name`.

## That's It

That's it. Five minutes of setup. I don't know why I waited so long to do this myself.
