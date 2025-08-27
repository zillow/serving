How to add new manifests:

1. Checkout a new branch in this repository.
2. Identify the upstream manifest urls, e.g.
    - https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml
    - https://github.com/knative-sandbox/net-istio/releases/download/knative-v1.7.1/net-istio.yaml
3. Create the corresponding folder structure and download manifest from the upstream URLs. Here's an example.
    ``` 
    curl -sLO https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml
    ```
4. Make sure the downloaded content is exactly the same, with commands in the following example.
    ```
    diff <(curl -sL https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml) <(cat serving-core.yaml)
    ```
5. Create pull request for review and merge. In PR description please add the upstream url link (and corresponding upstream release) so that reviewers can check.


For reviewers:
1. Make sure manifest content is exactly the same as upstream, with commands in the following example.
    ```
    diff <(curl -sL https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml) <(curl -s https://raw.githubusercontent.com/zillow/serving/zillow/manifests/zillow/serving-core/v1.7.4/serving-core.yaml)
    ```
