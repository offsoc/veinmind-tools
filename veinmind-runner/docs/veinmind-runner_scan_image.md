## veinmind-runner scan image

Scan image

### Synopsis

Scan image from multi source, include dockerd/containerd/registry

```
veinmind-runner scan image [flags] target
```

### Examples

```

1. scan dockerd image nginx:latest
veinmind-runner scan image dockerd:nginx:latest

2. scan containerd image bitnami/nginx:latest
veinmind-runner scan image containerd:bitnami/nginx:latest

3. scan public registry image library/ubuntu (all tag)
veinmind-runner scan image registry-image:library/ubuntu

4. scan private registry image example.com/app/market:v1.11.2
veinmind-runner scan image -c auth.toml registry-image:example.com/app/market:v1.11.2

5. use openai analyze result
veinmind-runner scan image --enable-analyze --openai-token  <your_openai_token> nginx:latest

6. use openai analyze result with yourself questions
veinmind-runner scan image --enable-analyze --openai-token  <your_openai_token> -p "explain what happened at this json" nginx:latest

7. scan private registry example.com （need admin privilege)
veinmind-runner scan image -c auth.toml registry:example.com

auth.toml format (yaml):
[[auths]]
	registry = "example.com"
	username = "<your-username>"
	password = "<your-password>"

8. scan tarball format image
veinmind-runner scan image tarball:/tmp/alpine.tar

```

### Options

```
  -c, --config string   auth config path
  -f, --filter string   catalog repo filter regex
  -h, --help            help for image
```

### Options inherited from parent commands

```
      --enable-analyze        auto use openai analyze result
  -e, --exit-code int         exit-code when veinmind-runner find security issues
      --format string         output format: html/json/cli (default "cli")
  -g, --glob string           specifies the pattern of plugin file to find
      --insecure-skip         skip tls config
      --openai-token string   auto openai analyze openai_key
  -o, --output string         output filepath of report
  -p, --prefix string         training openai limit sentence
      --threads int           threads for scan action (default 5)
  -v, --verbose               output verbose detail
```

### SEE ALSO

* [veinmind-runner scan](veinmind-runner_scan.md)	 - Scan cloud native objects security, include image/container/iac

###### Auto generated by spf13/cobra on 27-Mar-2023
