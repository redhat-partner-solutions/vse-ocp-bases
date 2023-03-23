# ZTP base

Inside the kustomization.yaml file we will declare all the required patches on the declarative YAML manifests of the ZTP workload cluster.

One key difference between the ztp kustomization.yaml compared to other bases is that SiteConfig manifest goes as it is under generators since each SiteConfig have parameters set according to its cluster requirement. 

resources contains a list of Resource Config file paths to be customized using patches whereas Generators contains a list of manifest to generate as it is.

generators:
 - SiteConfig-example-sno.yaml

resources:
  - ../../../base/ztp/site-config
