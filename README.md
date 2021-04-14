Primer to CI/CD in Gitlab
---

Components
---

- Gitlab server
- Gitlab runner
- `.gitlab-ci.yml` file

Gitlab server delegates the running of scripts in the Gitlab runner, which may save outputs to the defined artifact path

Gitlab runner clones your repository and executes the defined steps in the script

The `gitlab-ci.yml` file has to be at the root of the project

yaml stuff
--- 

Stages define the sequence of jobs

```
stages:
  - build
  - test
```

Jobs have different actions

```
build car:
  stage: <define stage>
  script:
    - <shell command>
  artifact:
    path:
      - <path to make persistent>
```

If no stages are defined in the jobs, it defaults to `test` stage

By putting different jobs with the same stage, they will execute in the order they are placed in the yml file
