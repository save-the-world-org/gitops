# save-the-world-org gitops

Infrared delivers save-the-world-org's Products from this repo. It writes, for each Product:

- products/<product>/build: the kpack Image that builds it;
- products/<product>/chart: its chart, yours to edit;
- products/<product>/zones/<zone>/values.yaml: each zone's values, including the image a Release pins;
- registry/clusters/google-cp-saas-v1/components/product-*.yaml: the Argo CD Applications.

Infrared applies the Applications in registry/clusters/google-cp-saas-v1/components itself, in
the Argo CD AppProject org-save-the-world-org, which only lets them deploy to save-the-world-org's zones from
save-the-world-org's repos. Other files in that directory are ignored.
