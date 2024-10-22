Responses Map
=============

# APPLICATION

| SERVICE                      | CODE            | ERROR                  |
|------------------------------|-----------------|------------------------|
| Document:Article             |                 |                        |
|                              | InvalidArgument | IDENTITY;EMPTY         |
|                              | InvalidArgument | IDENTITY;INVALID       |
|                              | NotFound        | ARTICLE                |
|                              | Internal        | ARTICLE                |
|                              | Internal        | CONTENTS               |
|------------------------------|-----------------|------------------------|
| Explore:Catalog              |                 |                        |
|                              | InvalidArgument | DATE;EMPTY             |
|                              | InvalidArgument | DATE;EXCEED            |
|                              | Internal        | CATALOG                |
|------------------------------|-----------------|------------------------|
| Explore:Discover             |                 |                        |
|                              | InvalidArgument | QUERY,TOPIC,TAGS;EMPTY |
|                              | InvalidArgument | QUERY;INVALID          |
|                              | InvalidArgument | TOPIC;INVALID          |
|                              | InvalidArgument | TAGS;INVALID           |
|                              | Internal        | DISCOVER               |
|------------------------------|-----------------|------------------------|
| Explore:Featured             |                 |                        |
|                              | Internal        | FEATURED               |
|------------------------------|-----------------|------------------------|
| Explore:Express              |                 |                        |
|                              | Internal        | EXPRESS                |
|                              | Internal        | CONTENTS               |
|------------------------------|-----------------|------------------------|
| Explore:Publisher            |                 |                        |
|                              | InvalidArgument | NAME;EMPTY             |
|                              | InvalidArgument | NAME;INVALID           |
|                              | Internal        | PUBLISHER              |
|------------------------------|-----------------|------------------------|
| Explore:Author               |                 |                        |
|                              | InvalidArgument | NAME;EMPTY             |
|                              | InvalidArgument | NAME;INVALID           |
|                              | Internal        | AUTHOR                 |
|------------------------------|-----------------|------------------------|
| Collection:Alias             |                 |                        |
|                              | InvalidArgument | ALIAS;INVALID          |
|                              | Internal        | ALIAS                  |
|------------------------------|-----------------|------------------------|
| Information:PublisherDetails |                 |                        |
|                              | InvalidArgument | NAME;EMPTY             |
|                              | InvalidArgument | NAME;INVALID           |
|                              | NotFound        | PUBLISHER              |
|                              | Internal        | PUBLISHER              |
|------------------------------|-----------------|------------------------|
| Information:AuthorDetails    |                 |                        |
|                              | InvalidArgument | NAME;EMPTY             |
|                              | InvalidArgument | NAME;INVALID           |
|                              | NotFound        | AUTHOR                 |
|                              | Internal        | AUTHOR                 |
|------------------------------|-----------------|------------------------|





----------------------------------------------------------------------------------------------------

# ADMINISTRATION

| CODE             | ERROR                  |
|------------------|------------------------|
| Unavailable      | connection error: ...  |
|------------------|------------------------|



## SERVICES

| SERVICE                      | CODE               | ERROR                         |
|------------------------------|--------------------|-------------------------------|
| DocumentExplore              |                    |                               |
|                              | InvalidArgument    | DATE;EMPTY                    |
|                              | InvalidArgument    | DATE;EXCEED                   |
|                              | Internal           | EXPLORE                       |
|------------------------------|--------------------|-------------------------------|
| Topics                       |                    |                               |
|                              | Internal           | TOPICS                        |
|------------------------------|--------------------|-------------------------------|
| Publishers                   |                    |                               |
|                              | Internal           | PUBLISHERS                    |
|------------------------------|--------------------|-------------------------------|
| Authors                      |                    |                               |
|                              | Internal           | AUTHORS                       |
|------------------------------|--------------------|-------------------------------|
| Authenticate                 |                    |                               |
|                              | InvalidArgument    | EMAIL;EMPTY                   |
|                              | InvalidArgument    | EMAIL;INVALID                 |
|                              | InvalidArgument    | PASSWORD;EMPTY                |
|                              | InvalidArgument    | PASSWORD;INVALID              |
|                              | Internal           | AUTHENTICATE                  |
|                              | Unauthenticated    | CRITERIA                      |
|                              | PermissionDenied   | DISABLED                      |
|------------------------------|--------------------|-------------------------------|
| DocumentArticleAdd           |                    |                               |
|                              | Internal           | IDENTITY                      |
|                              | Internal           | DOCUMENT                      |
|                              | AlreadyExists      | DOCUMENT                      |
|                              | FailedPrecondition | AUTHOR_ID                     |
|                              | AlreadyExists      | EXTRACT                       |
|                              | Internal           | MEMORY                        |
|------------------------------|--------------------|-------------------------------|
| SetDocumentState             |                    |                               |
|                              | InvalidArgument    | ID;EMPTY                      |
|                              | InvalidArgument    | STATE;UNSPECIFIED             |
|                              | Internal           | STATE                         |
|                              | Internal           | DOCUMENT                      |
|                              | Internal           | MEMORY/CATALOG                |
|                              | Internal           | MEMORY/DOCUMENT               |
|------------------------------|--------------------|-------------------------------|
| DocumentReview               |                    |                               |
|                              | InvalidArgument    | ID                            |
|                              | Internal           | DOCUMENT                      |
|                              | Internal           | CONTENT                       |
|------------------------------|--------------------|-------------------------------|
| DocumentSummary              |                    |                               |
|                              | InvalidArgument    | ID                            |
|                              | Internal           | DOCUMENT                      |
|------------------------------|--------------------|-------------------------------|
| PublisherAdd                 |                    |                               |
|                              | Internal           | PUBLISHER                     |
|                              | InvalidArgument    | NAME;EMPTY                    |
|                              | InvalidArgument    | WEBSITE;EMPTY                 |
|                              | InvalidArgument    | WEBSITE;INVALID               |
|                              | InvalidArgument    | LOGO;EMPTY                    |
|                              | AlreadyExists      | PUBLISHER                     |
|------------------------------|--------------------|-------------------------------|
| AuthorAdd                    |                    |                               |
|                              | Internal           | AUTHOR                        |
|                              | InvalidArgument    | ROLE;UNSPECIFIED              |
|                              | InvalidArgument    | NAME;EMPTY                    |
|                              | InvalidArgument    | EMAIL;EMPTY                   |
|                              | InvalidArgument    | PASSWORD;EMPTY                |
|                              | AlreadyExists      | AUTHOR                        |
|------------------------------|--------------------|-------------------------------|
| DocumentUpdate               |                    |                               |
|                              | InvalidArgument    | ID;EMPTY                      |
|                              | InvalidArgument    | HEADLINE;EMPTY                |
|                              | InvalidArgument    | CONTENT;EMPTY                 |
|                              | Internal           | DOCUMENT                      |
|                              | Internal           | UPDATE                        |
|                              | Internal           | MEMORY/CATALOG                |
|                              | Internal           | MEMORY/DOCUMENT               |
|------------------------------|--------------------|-------------------------------|
| ParaphraseAdd                |                    |                               |
|                              | InvalidArgument    | ID;EMPTY                      |
|                              | InvalidArgument    | HEADLINE;EMPTY                |
|                              | InvalidArgument    | CONTENT;EMPTY                 |
|                              | Internal           | DOCUMENT                      |
|                              | Internal           | PARAPHRASE                    |
|                              | Internal           | MEMORY/CATALOG                |
|                              | Internal           | MEMORY/DOCUMENT               |
|------------------------------|--------------------|-------------------------------|
| ExploreArticles              |                    |                               |
|                              | InvalidArgument    | DATE;EMPTY                    |
|                              | InvalidArgument    | DATE;EXCEED                   |
|                              | Internal           | EXPLORE                       |
|------------------------------|--------------------|-------------------------------|



## INTERCEPTORS

| INTERCEPTOR                  | CODE             | ERROR                         |
|------------------------------|------------------|-------------------------------|
| Authorization                |                  |                               |
|                              | Unauthenticated  | INTRC/AUTHZ;METADATA;EMPTY    |
|                              | Unauthenticated  | INTRC/AUTHZ;TOKEN;EMPTY       |
|                              | Unauthenticated  | INTRC/AUTHZ;TOKEN             |
|                              | NotFound         | INTRC/AUTHZ;ENDPOINT          |
|                              | PermissionDenied | INTRC/AUTHZ;ENDPOINT          |
|                              | NotFound         | INTRC/AUTHZ;ROLE              |
|                              | PermissionDenied | INTRC/AUTHZ;ROLE              |
|                              | NotFound         | INTRC/AUTHZ;ID                |
|------------------------------|------------------|-------------------------------|
