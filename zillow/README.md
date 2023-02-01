How to add new manifests:

1. Checkout a new branch
2. Get upstream manifest urls, e.g.
    - https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml
    - https://github.com/knative-sandbox/net-istio/releases/download/knative-v1.7.1/net-istio.yaml
3. Create corresponding folder structure and download manifest from above urls
    ``` 
    curl -sL https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml
    ```
4. Make sure the downloaded content is exactly the same
    ```
    diff <(curl -sL https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml) <(cat serving-core/v1.7.4/serving-core.yaml)
    ```
5. Create pull request for review and merge. In PR description please add the upstream url link (and corresponding upstream release) so that reviewers can check.


For reviewers:
1. Make sure manifest content is exactly the same as upstream
    ```
    diff <(curl -sL https://github.com/knative/serving/releases/download/knative-v1.7.4/serving-core.yaml) <(curl -s https://raw.githubusercontent.com/zillow/serving/zillow/manifests/zillow/serving-core/v1.7.4/serving-core.yaml)
    ```
