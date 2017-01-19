# cf-example-image-metadata

| Pipeline name   | Last build status  |
|---|---|
| cf-example-image-metadata | [![Codefresh build status]( https://g.codefresh.io/api/badges/build?repoOwner=codefreshdemo&repoName=cf-example-image-metadata&branch=master&pipelineName=cf-example-image-metadata&accountName=nikolai&type=cf-1)]( https://g.codefresh.io/repositories/codefreshdemo/cf-example-image-metadata/builds?filter=trigger:build;branch:master;service:588070a7663ea90100aedb92~cf-example-image-metadata) |

## Image Metadata Annotations
Images built by Codefresh may be annotated with an array of key-value metadata.
Metadata values may be:

#### 1. Strings.
#### 2. Numbers.
#### 3. Booleans.
#### 4. Expression evaluations.

## Build Phase Image Metadata Annotation
You may annotate an image as part of its build process by declaring on the Build step:

#### 1. The metadata attribute
#### 2. The set operation.
#### 3. An array of key-value metadata.

```yml
build_step:
  type: build
  ...
  metadata: # Declare the metadata attribute
    set: # Specify the set operation
      - qa: pending
      - commit_message: ${{CF_COMMIT_MESSAGE}}
      - exit_code: 0
      - is_main:
          evaluate: "'${{CF_BRANCH}}' == 'main'"
```