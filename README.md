# Saleor Helm Charts

This is an unofficial registry of [Saleor](https://saleorprotocol.com/) [helm](https://helm.sh/) charts.

## Prerequisites
* [Helm](https://helm.sh/) 3+

## Setup

Add the saleor helm repo:
```
helm repo add saleor https://k.github.io/saleor-helm
helm repo update
```

Then configure a values.yaml for the chart you want to install.

## List of Charts

### [saleor](./charts/saleor)

Chart to run [Saleor](https://github.com/mirumee/saleor) with the [Dashboard](###dashboard) and [Storefront](###storefront).

### [dashboard](./charts/dashboard)

Chart to run [Saleor Dashboard]()

### [storefront](./charts/storefront)

Chart to run [Saleor Storefront](https://github.com/mirumee/saleor-storefront).

## Deploy to Github Pages

Deploy requires [`cr`](https://github.com/helm/chart-releaser) tool 

### Enable Github Pages (only first time)

Settings > Options > Github Pages > Source > Select master branch

### Package chart

```
helm package charts/<chart-to-package> --destination .deploy
```

### Upload New Release

```
cr upload --config config.yaml --token <deploy-token>
```

### Generate new index
```
cr index --config config.yaml
git add index.yaml
git commit -m "Update index.yaml"
git push
```