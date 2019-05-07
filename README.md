# ![LOGO](logo.png) Bitbucket **flow**ground Connector

## Description

A generated **flow**ground connector for the Bitbucket API (version 2.0).

Generated from: https://api.apis.guru/v2/specs/bitbucket.org/2.0/swagger.json<br/>
Generated at: 2019-05-07T17:39:44+03:00

## API Description

Code against the Bitbucket API to automate simple tasks, embed Bitbucket data into your own site, build mobile or desktop apps, or even add custom UI add-ons into Bitbucket itself using the Connect framework.

## Authorization

Supported authorization schemes:
- API Key- Basic Authentication
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### delete_addon

*Tags:* `addon`

### put_addon

*Tags:* `addon`

### get_addon_linkers

*Tags:* `addon`

### get_addon_linkers__linker_key_

*Tags:* `addon`

#### Input Parameters
* `linker_key` - _required_

### delete_addon_linkers__linker_key__values

*Tags:* `addon`

#### Input Parameters
* `linker_key` - _required_

### get_addon_linkers__linker_key__values

*Tags:* `addon`

#### Input Parameters
* `linker_key` - _required_

### post_addon_linkers__linker_key__values

*Tags:* `addon`

#### Input Parameters
* `linker_key` - _required_

### put_addon_linkers__linker_key__values

*Tags:* `addon`

#### Input Parameters
* `linker_key` - _required_

### delete_addon_linkers__linker_key__values_

*Tags:* `addon`

#### Input Parameters
* `linker_key` - _required_

### get_addon_linkers__linker_key__values_

*Tags:* `addon`

#### Input Parameters
* `linker_key` - _required_

### Returns the webhook resource or subject types on which webhooks can<br/>
> be registered.<br/>
> <br/>
> Each resource/subject type contains an `events` link that returns the<br/>
> paginated list of specific events each individual subject type can<br/>
> emit.<br/>
> <br/>
> This endpoint is publicly accessible and does not require<br/>
> authentication or scopes.<br/>
> <br/>
> Example:<br/>
> <br/>
> ```<br/>
> $ curl https://api.bitbucket.org/2.0/hook_events<br/>
> <br/>
> {<br/>
>     "repository": {<br/>
>         "links": {<br/>
>             "events": {<br/>
>                 "href": "https://api.bitbucket.org/2.0/hook_events/repository"<br/>
>             }<br/>
>         }<br/>
>     },<br/>
>     "team": {<br/>
>         "links": {<br/>
>             "events": {<br/>
>                 "href": "https://api.bitbucket.org/2.0/hook_events/team"<br/>
>             }<br/>
>         }<br/>
>     },<br/>
>     "user": {<br/>
>         "links": {<br/>
>             "events": {<br/>
>                 "href": "https://api.bitbucket.org/2.0/hook_events/user"<br/>
>             }<br/>
>         }<br/>
>     }<br/>
> }<br/>
> ```

*Tags:* `webhooks`

### Returns a paginated list of all valid webhook events for the<br/>
> specified entity.<br/>
> <br/>
> This is public data that does not require any scopes or authentication.<br/>
> <br/>
> Example:<br/>
> <br/>
> NOTE: The following example is a truncated response object for the `team` `subject_type`.<br/>
> We return the same structure for the other `subject_type` objects.<br/>
> <br/>
> ```<br/>
> $ curl https://api.bitbucket.org/2.0/hook_events/team<br/>
> {<br/>
>     "page": 1,<br/>
>     "pagelen": 30,<br/>
>     "size": 21,<br/>
>     "values": [<br/>
>         {<br/>
>             "category": "Repository",<br/>
>             "description": "Whenever a repository push occurs",<br/>
>             "event": "repo:push",<br/>
>             "label": "Push"<br/>
>         },<br/>
>         {<br/>
>             "category": "Repository",<br/>
>             "description": "Whenever a repository fork occurs",<br/>
>             "event": "repo:fork",<br/>
>             "label": "Fork"<br/>
>         },<br/>
>         ...<br/>
>         {<br/>
>             "category": "Repository",<br/>
>             "description": "Whenever a repository import occurs",<br/>
>             "event": "repo:imported",<br/>
>             "label": "Import"<br/>
>         }<br/>
>     ]<br/>
> }<br/>
> ```

*Tags:* `webhooks`

#### Input Parameters
* `subject_type` - _required_ - A resource or subject type.
    Possible values: user, repository, team.

### Returns a paginated list of all public repositories.<br/>
> <br/>
> This endpoint also supports filtering and sorting of the results. See<br/>
> [filtering and sorting](../meta/filtering) for more details.

*Tags:* `repositories`

#### Input Parameters
* `after` - _optional_ - Filter the results to include only repositories create on or
after this [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601)
 timestamp. Example: `YYYY-MM-DDTHH:mm:ss.sssZ`

### Returns a paginated list of all repositories owned by the specified<br/>
> account or UUID.<br/>
> <br/>
> The result can be narrowed down based on the authenticated user's role.<br/>
> <br/>
> E.g. with `?role=contributor`, only those repositories that the<br/>
> authenticated user has write access to are returned (this includes any<br/>
> repo the user is an admin on, as that implies write access).<br/>
> <br/>
> This endpoint also supports filtering and sorting of the results. See<br/>
> [filtering and sorting](../../meta/filtering) for more details.

*Tags:* `repositories`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `role` - _optional_ - 
Filters the result based on the authenticated user's role on each repository.

* **member**: returns repositories to which the user has explicit read access
* **contributor**: returns repositories to which the user has explicit write access
* **admin**: returns repositories to which the user has explicit administrator access
* **owner**: returns all repositories owned by the current user

    Possible values: admin, contributor, member, owner.

### Deletes the repository. This is an irreversible operation.<br/>
> <br/>
> This does not affect its forks.

*Tags:* `repositories`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.


### Returns the object describing this repository.

*Tags:* `repositories`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.


### Creates a new repository.<br/>
> <br/>
> Note: In order to set the project for the newly created repository,<br/>
> pass in either the project key or the project UUID as part of the<br/>
> request body as shown in the examples below:<br/>
> <br/>
> ```<br/>
> $ curl -X POST -H "Content-Type: application/json" -d '{<br/>
>     "scm": "git",<br/>
>     "project": {<br/>
>         "key": "MARS"<br/>
>     }<br/>
> }' https://api.bitbucket.org/2.0/repositories/teamsinspace/hablanding<br/>
> ```<br/>
> <br/>
> or<br/>
> <br/>
> ```<br/>
> $ curl -X POST -H "Content-Type: application/json" -d '{<br/>
>     "scm": "git",<br/>
>     "project": {<br/>
>         "key": "{ba516952-992a-4c2d-acbd-17d502922f96}"<br/>
>     }<br/>
> }' https://api.bitbucket.org/2.0/repositories/teamsinspace/hablanding<br/>
> ```<br/>
> <br/>
> The project must only be assigned for repositories belonging to a team.<br/>
> If the repository owner is a team and the project is not provided, the<br/>
> repository is automatically assigned to the oldest project in the team.<br/>
> <br/>
> Note: In the examples above, the username `teamsinspace`,<br/>
> and/or the repository name `hablanding` can be replaced by UUIDs.

*Tags:* `repositories`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.


### Since this endpoint can be used to both update and to create a<br/>
> repository, the request body depends on the intent.<br/>
> <br/>
> ### Creation<br/>
> <br/>
> See the POST documentation for the repository endpoint for an example<br/>
> of the request body.<br/>
> <br/>
> ### Update<br/>
> <br/>
> Note: Changing the `name` of the repository will cause the location to<br/>
> be changed. This is because the URL of the repo is derived from the<br/>
> name (a process called slugification). In such a scenario, it is<br/>
> possible for the request to fail if the newly created slug conflicts<br/>
> with an existing repository's slug. But if there is no conflict,<br/>
> the new location will be returned in the `Location` header of the<br/>
> response.

*Tags:* `repositories`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.


### Returns a paginated list of all branch restrictions on the<br/>
> repository.

*Tags:* `branchrestrictions`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Creates a new branch restriction rule for a repository.<br/>
> <br/>
> `kind` describes what will be restricted. Allowed values are: `push`,<br/>
> `force`, `delete`, and `restrict_merges`.<br/>
> <br/>
> Different kinds of branch restrictions have different requirements:<br/>
> <br/>
> * `push` and `restrict_merges` require `users` and `groups` to be<br/>
>   specified. Empty lists are allowed, in which case permission is<br/>
>   denied for everybody.<br/>
> * `force` can not be specified in a Mercurial repository.<br/>
> <br/>
> `pattern` is used to determine which branches will be restricted.<br/>
> <br/>
> A `'*'` in `pattern` will expand to match zero or more characters, and<br/>
> every other character matches itself. For example, `'foo*'` will match<br/>
> `'foo'` and `'foobar'`, but not `'barfoo'`. `'*'` will match all<br/>
> branches.<br/>
> <br/>
> `users` and `groups` are lists of user names and group names.<br/>
> <br/>
> `kind` and `pattern` must be unique within a repository; adding new<br/>
> users or groups to an existing restriction should be done via `PUT`.<br/>
> <br/>
> Note that branch restrictions with overlapping patterns are allowed,<br/>
> but the resulting behavior may be surprising.

*Tags:* `branchrestrictions`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Deletes an existing branch restriction rule.

*Tags:* `branchrestrictions`

#### Input Parameters
* `id` - _required_ - The restriction rule's id
* `id` - _required_
* `repo_slug` - _required_

### Returns a specific branch restriction rule.

*Tags:* `branchrestrictions`

#### Input Parameters
* `id` - _required_ - The restriction rule's id
* `id` - _required_
* `repo_slug` - _required_

### Updates an existing branch restriction rule.<br/>
> <br/>
> Fields not present in the request body are ignored.<br/>
> <br/>
> See [`POST`](../../branch-restrictions#post) for details.

*Tags:* `branchrestrictions`

#### Input Parameters
* `id` - _required_ - The restriction rule's id
* `id` - _required_
* `repo_slug` - _required_

### Redact the authenticated user's approval of the specified commit.<br/>
> <br/>
> This operation is only available to users that have explicit access to<br/>
> the repository. In contrast, just the fact that a repository is<br/>
> publicly accessible to users does not give them the ability to approve<br/>
> commits.

*Tags:* `commits`

#### Input Parameters
* `node` - _required_ - The commit's SHA1.
* `node` - _required_
* `repo_slug` - _required_

### Approve the specified commit as the authenticated user.<br/>
> <br/>
> This operation is only available to users that have explicit access to<br/>
> the repository. In contrast, just the fact that a repository is<br/>
> publicly accessible to users does not give them the ability to approve<br/>
> commits.

*Tags:* `commits`

#### Input Parameters
* `node` - _required_ - The commit's SHA1.
* `node` - _required_
* `repo_slug` - _required_

### Returns all statuses (e.g. build results) for a specific commit.

*Tags:* `repositories` `commitstatuses`

#### Input Parameters
* `node` - _required_ - The commit's SHA1
* `node` - _required_
* `repo_slug` - _required_

### Creates a new build status against the specified commit.<br/>
> <br/>
> If the specified key already exists, the existing status object will<br/>
> be overwritten.<br/>
> <br/>
> When creating a new commit status, you can use a URI template for the URL.<br/>
> Templates are URLs that contain variable names that Bitbucket will<br/>
> evaluate at runtime whenever the URL is displayed anywhere similar to<br/>
> parameter substitution in<br/>
> [Bitbucket Connect](https://developer.atlassian.com/bitbucket/concepts/context-parameters.html).<br/>
> For example, one could use `https://foo.com/builds/{repository.full_name}`<br/>
> which Bitbucket will turn into `https://foo.com/builds/foo/bar` at render time.<br/>
> The context variables available are `repository` and `commit`.

*Tags:* `repositories` `commitstatuses`

#### Input Parameters
* `node` - _required_ - The commit's SHA1
* `node` - _required_
* `repo_slug` - _required_

### Returns the specified build status for a commit.

*Tags:* `repositories` `commitstatuses`

#### Input Parameters
* `node` - _required_ - The commit's SHA1
* `key` - _required_ - The build status' unique key
* `key` - _required_
* `repo_slug` - _required_

### Used to update the current status of a build status object on the<br/>
> specific commit.<br/>
> <br/>
> This operation can also be used to change other properties of the<br/>
> build status:<br/>
> <br/>
> * `state`<br/>
> * `name`<br/>
> * `description`<br/>
> * `url`<br/>
> * `refname`<br/>
> <br/>
> The `key` cannot be changed.

*Tags:* `repositories` `commitstatuses`

#### Input Parameters
* `node` - _required_ - The commit's SHA1
* `key` - _required_ - The commit status' unique key
* `key` - _required_
* `repo_slug` - _required_

### Returns the specified commit.

*Tags:* `commits`

#### Input Parameters
* `revision` - _required_ - The commit's SHA1.
* `revision` - _required_
* `repo_slug` - _required_

### Returns the commit's comments.<br/>
> <br/>
> This includes both global and inline comments.<br/>
> <br/>
> The default sorting is oldest to newest and can be overridden with<br/>
> the `sort` query parameter.

*Tags:* `commits`

#### Input Parameters
* `username` - _required_
* `sha` - _required_
* `repo_slug` - _required_

### Returns the specified commit comment.

*Tags:* `commits`

#### Input Parameters
* `username` - _required_
* `sha` - _required_
* `comment_id` - _required_
* `repo_slug` - _required_

### These are the repository's commits. They are paginated and returned<br/>
> in reverse chronological order, similar to the output of `git log` and<br/>
> `hg log`. Like these tools, the DAG can be filtered.<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/<br/>
> <br/>
> Returns all commits in the repo in topological order (newest commit<br/>
> first). All branches and tags are included (similar to<br/>
> `git log --all` and `hg log`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/master<br/>
> <br/>
> Returns all commits on rev `master` (similar to `git log master`,<br/>
> `hg log master`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/dev?exclude=master<br/>
> <br/>
> Returns all commits on ref `dev`, except those that are reachable on<br/>
> `master` (similar to `git log dev ^master`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/?exclude=master<br/>
> <br/>
> Returns all commits in the repo that are not on master<br/>
> (similar to `git log --all ^master`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/?include=foo&include=bar&exclude=fu&exclude=fubar<br/>
> <br/>
> Returns all commits that are on refs `foo` or `bar`, but not on `fu` or<br/>
> `fubar` (similar to `git log foo bar ^fu ^fubar`).<br/>
> <br/>
> Because the response could include a very large number of commits, it<br/>
> is paginated. Follow the 'next' link in the response to navigate to the<br/>
> next page of commits. As with other paginated resources, do not<br/>
> construct your own links.<br/>
> <br/>
> When the include and exclude parameters are more than can fit in a<br/>
> query string, clients can use a `x-www-form-urlencoded` POST instead.

*Tags:* `commits`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Identical to `GET /repositories/{username}/{repo_slug}/commits`,<br/>
> except that POST allows clients to place the include and exclude<br/>
> parameters in the request body to avoid URL length issues.<br/>
> <br/>
> **Note that this resource does NOT support new commit creation.**

*Tags:* `commits`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### These are the repository's commits. They are paginated and returned<br/>
> in reverse chronological order, similar to the output of `git log` and<br/>
> `hg log`. Like these tools, the DAG can be filtered.<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/<br/>
> <br/>
> Returns all commits in the repo in topological order (newest commit<br/>
> first). All branches and tags are included (similar to<br/>
> `git log --all` and `hg log`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/master<br/>
> <br/>
> Returns all commits on rev `master` (similar to `git log master`,<br/>
> `hg log master`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/dev?exclude=master<br/>
> <br/>
> Returns all commits on ref `dev`, except those that are reachable on<br/>
> `master` (similar to `git log dev ^master`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/?exclude=master<br/>
> <br/>
> Returns all commits in the repo that are not on master<br/>
> (similar to `git log --all ^master`).<br/>
> <br/>
> ## GET /repositories/{username}/{repo_slug}/commits/?include=foo&include=bar&exclude=fu&exclude=fubar<br/>
> <br/>
> Returns all commits that are on refs `foo` or `bar`, but not on `fu` or<br/>
> `fubar` (similar to `git log foo bar ^fu ^fubar`).<br/>
> <br/>
> Because the response could include a very large number of commits, it<br/>
> is paginated. Follow the 'next' link in the response to navigate to the<br/>
> next page of commits. As with other paginated resources, do not<br/>
> construct your own links.<br/>
> <br/>
> When the include and exclude parameters are more than can fit in a<br/>
> query string, clients can use a `x-www-form-urlencoded` POST instead.

*Tags:* `commits`

#### Input Parameters
* `username` - _required_
* `revision` - _required_
* `repo_slug` - _required_

### Identical to `GET /repositories/{username}/{repo_slug}/commits`,<br/>
> except that POST allows clients to place the include and exclude<br/>
> parameters in the request body to avoid URL length issues.<br/>
> <br/>
> **Note that this resource does NOT support new commit creation.**

*Tags:* `commits`

#### Input Parameters
* `username` - _required_
* `revision` - _required_
* `repo_slug` - _required_

### Returns the components that have been defined in the issue tracker.<br/>
> <br/>
> This resource is only available on repositories that have the issue<br/>
> tracker enabled.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Returns the specified issue tracker component object.

*Tags:* `issue_tracker`

#### Input Parameters
* `component_id` - _required_ - The component's id
* `component_id` - _required_
* `repo_slug` - _required_

### Returns the repository's default reviewers.<br/>
> <br/>
> These are the users that are automatically added as reviewers on every<br/>
> new pull request that is created.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Removes a default reviewer from the repository.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `target_username` - _required_
* `repo_slug` - _required_

### Returns the specified reviewer.<br/>
> <br/>
> This can be used to test whether a user is among the repository's<br/>
> default reviewers list. A 404 indicates that that specified user is not<br/>
> a default reviewer.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `target_username` - _required_
* `repo_slug` - _required_

### Adds the specified user to the repository's list of default<br/>
> reviewers.<br/>
> <br/>
> This method is idempotent. Adding a user a second time has no effect.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `target_username` - _required_
* `repo_slug` - _required_

### Produces a raw, git-style diff for either a single commit (diffed<br/>
> against its first parent), or a revspec of 2 commits (e.g.<br/>
> `3a8b42..9ff173` where the first commit represents the source and the<br/>
> second commit the destination).<br/>
> <br/>
> In case of the latter (diffing a revspec), a 3-way diff, or merge diff,<br/>
> is computed. This shows the changes introduced by the left branch<br/>
> (`3a8b42` in our example) as compared againt the right branch<br/>
> (`9ff173`).<br/>
> <br/>
> This is equivalent to merging the left branch into the right branch and<br/>
> then computing the diff of the merge commit against its first parent<br/>
> (the right branch). This follows the same behavior as pull requests<br/>
> that also show this style of 3-way, or merge diff.<br/>
> <br/>
> While similar to patches, diffs:<br/>
> <br/>
> * Don't have a commit header (username, commit message, etc)<br/>
> * Support the optional `path=foo/bar.py` query param to filter<br/>
>   the diff to just that one file diff<br/>
> <br/>
> The raw diff is returned as-is, in whatever encoding the files in the<br/>
> repository use. It is not decoded into unicode. As such, the<br/>
> content-type is `text/plain`.

*Tags:* `commits`

#### Input Parameters
* `context` - _optional_ - Generate diffs with <n> lines of context instead of the usual three
* `path` - _optional_ - Limit the diff to a single file
* `repo_slug` - _required_

### Returns a list of download links associated with the repository.

*Tags:* `downloads`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Upload new download artifacts.<br/>
> <br/>
> To upload files, perform a `multipart/form-data` POST containing one<br/>
> or more `files` fields:<br/>
> <br/>
>     $ echo Hello World > hello.txt<br/>
>     $ curl -s -u evzijst -X POST https://api.bitbucket.org/2.0/repositories/evzijst/git-tests/downloads -F files=@hello.txt<br/>
> <br/>
> When a file is uploaded with the same name as an existing artifact,<br/>
> then the existing file will be replaced.

*Tags:* `downloads`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Deletes the specified download artifact from the repository.

*Tags:* `downloads`

#### Input Parameters
* `username` - _required_
* `filename` - _required_
* `repo_slug` - _required_

### Return a redirect to the contents of a download artifact.<br/>
> <br/>
> This endpoint returns the actual file contents and not the artifact's<br/>
> metadata.<br/>
> <br/>
>     $ curl -s -L https://api.bitbucket.org/2.0/repositories/evzijst/git-tests/downloads/hello.txt<br/>
>     Hello World

*Tags:* `downloads`

#### Input Parameters
* `username` - _required_
* `filename` - _required_
* `repo_slug` - _required_

### Returns a paginated list of all the forks of the specified<br/>
> repository.

*Tags:* `repositories`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Returns a paginated list of webhooks installed on this repository.

*Tags:* `repositories` `webhooks`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Creates a new webhook on the specified repository.<br/>
> <br/>
> Example:<br/>
> <br/>
> ```<br/>
> $ curl -X POST -u credentials -H 'Content-Type: application/json'           https://api.bitbucket.org/2.0/repositories/username/slug/hooks           -d '<br/>
>     {<br/>
>       "description": "Webhook Description",<br/>
>       "url": "https://example.com/",<br/>
>       "active": true,<br/>
>       "events": [<br/>
>         "repo:push",<br/>
>         "issue:created",<br/>
>         "issue:updated"<br/>
>       ]<br/>
>     }'<br/>
> ```<br/>
> <br/>
> Note that this call requires the webhook scope, as well as any scope<br/>
> that applies to the events that the webhook subscribes to. In the<br/>
> example above that means: `webhook`, `repository` and `issue`.<br/>
> <br/>
> Also note that the `url` must properly resolve and cannot be an<br/>
> internal, non-routed address.

*Tags:* `repositories` `webhooks`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Deletes the specified webhook subscription from the given<br/>
> repository.

*Tags:* `repositories` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id
* `uid` - _required_
* `repo_slug` - _required_

### Returns the webhook with the specified id installed on the specified<br/>
> repository.

*Tags:* `repositories` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id.
* `uid` - _required_
* `repo_slug` - _required_

### Updates the specified webhook subscription.<br/>
> <br/>
> The following properties can be mutated:<br/>
> <br/>
> * `description`<br/>
> * `url`<br/>
> * `active`<br/>
> * `events`

*Tags:* `repositories` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id
* `uid` - _required_
* `repo_slug` - _required_

### Returns the issues in the issue tracker.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Creates a new issue.<br/>
> <br/>
> This call requires authentication. Private repositories or private<br/>
> issue trackers require the caller to authenticate with an account that<br/>
> has appropriate authorisation.<br/>
> <br/>
> The authenticated user is used for the issue's `reporter` field.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Deletes the specified issue. This requires write access to the<br/>
> repository.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `issue_id` - _required_
* `repo_slug` - _required_

### Returns the specified issue.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `issue_id` - _required_
* `repo_slug` - _required_

### Returns all attachments for this issue.<br/>
> <br/>
> This returns the files' meta data. This does not return the files'<br/>
> actual contents.<br/>
> <br/>
> The files are always ordered by their upload date.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Upload new issue attachments.<br/>
> <br/>
> To upload files, perform a `multipart/form-data` POST containing one<br/>
> or more file fields.<br/>
> <br/>
> When a file is uploaded with the same name as an existing attachment,<br/>
> then the existing file will be replaced.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Deletes an attachment.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `path` - _required_
* `issue_id` - _required_
* `repo_slug` - _required_

### Returns the contents of the specified file attachment.<br/>
> <br/>
> Note that this endpoint does not return a JSON response, but instead<br/>
> returns a redirect pointing to the actual file that in turn will return<br/>
> the raw contents.<br/>
> <br/>
> The redirect URL contains a one-time token that has a limited lifetime.<br/>
> As a result, the link should not be persisted, stored, or shared.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `path` - _required_
* `issue_id` - _required_
* `repo_slug` - _required_

### Returns all comments that were made on the specified issue.<br/>
> <br/>
> The default sorting is oldest to newest and can be overridden with<br/>
> the `sort` query parameter.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `issue_id` - _required_
* `repo_slug` - _required_

### Returns the specified issue comment object.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `comment_id` - _required_
* `issue_id` - _required_
* `repo_slug` - _required_

### Retract your vote.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Check whether the authenticated user has voted for this issue.<br/>
> A 204 status code indicates that the user has voted, while a 404<br/>
> implies they haven't.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Vote for this issue.<br/>
> <br/>
> To cast your vote, do an empty PUT. The 204 status code indicates that<br/>
> the operation was successful.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Stop watching this issue.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Indicated whether or not the authenticated user is watching this<br/>
> issue.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Start watching this issue.<br/>
> <br/>
> To start watching this issue, do an empty PUT. The 204 status code<br/>
> indicates that the operation was successful.

*Tags:* `issue_tracker`

#### Input Parameters
* `issue_id` - _required_ - The issue's id
* `issue_id` - _required_
* `repo_slug` - _required_

### Returns the milestones that have been defined in the issue tracker.<br/>
> <br/>
> This resource is only available on repositories that have the issue<br/>
> tracker enabled.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Returns the specified issue tracker milestone object.

*Tags:* `issue_tracker`

#### Input Parameters
* `milestone_id` - _required_ - The milestone's id
* `milestone_id` - _required_
* `repo_slug` - _required_

### Produces a raw patch for a single commit (diffed against its first<br/>
> parent), or a patch-series for a revspec of 2 commits (e.g.<br/>
> `3a8b42..9ff173` where the first commit represents the source and the<br/>
> second commit the destination).<br/>
> <br/>
> In case of the latter (diffing a revspec), a patch series is returned<br/>
> for the commits on the source branch (`3a8b42` and its ancestors in<br/>
> our example). For Mercurial, a single patch is returned that combines<br/>
> the changes of all commits on the source branch.<br/>
> <br/>
> While similar to diffs, patches:<br/>
> <br/>
> * Have a commit header (username, commit message, etc)<br/>
> * Do not support the `path=foo/bar.py` query parameter<br/>
> <br/>
> The raw patch is returned as-is, in whatever encoding the files in the<br/>
> repository use. It is not decoded into unicode. As such, the<br/>
> content-type is `text/plain`.

*Tags:* `commits`

#### Input Parameters
* `username` - _required_
* `spec` - _required_
* `repo_slug` - _required_

### Find pipelines

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Endpoint to create and initiate a pipeline. <br/>
> There are a couple of different options to initiate a pipeline, where the payload of the request will determine which type of pipeline will be instantiated.<br/>
> # Trigger a Pipeline for a branch or tag<br/>
> One way to trigger pipelines is by specifying the reference for which you want to trigger a pipeline (e.g. a branch or tag). <br/>
> The specified reference will be used to determine which pipeline definition from the `bitbucket-pipelines.yml` file will be applied to initiate the pipeline. The pipeline will then do a clone of the repository and checkout the latest revision of the specified reference.<br/>
> <br/>
> ### Example<br/>
> <br/>
> ```<br/>
> $ curl -X POST -is -u username:password \<br/>
>   -H 'Content-Type: application/json' \<br/>
>  https://api.bitbucket.org/2.0/repositories/jeroendr/meat-demo2/pipelines/ \<br/>
>   -d '<br/>
>   {<br/>
>     "target": {<br/>
>       "ref_type": "branch", <br/>
>       "type": "pipeline_ref_target", <br/>
>       "ref_name": "master"<br/>
>     }<br/>
>   }'<br/>
> ```<br/>
> # Trigger a Pipeline for a commit on a branch or tag<br/>
> You can initiate a pipeline for a specific commit and in the context of a specified reference (e.g. a branch, tag or bookmark).<br/>
> The specified reference will be used to determine which pipeline definition from the bitbucket-pipelines.yml file will be applied to initiate the pipeline. The pipeline will clone the repository and then do a checkout the specified reference. <br/>
> <br/>
> The following reference types are supported:<br/>
> <br/>
> * `branch` <br/>
> * `named_branch`<br/>
> * `bookmark` <br/>
>  * `tag`<br/>
> <br/>
> ### Example<br/>
> <br/>
> ```<br/>
> $ curl -X POST -is -u username:password \<br/>
>   -H 'Content-Type: application/json' \<br/>
>   https://api.bitbucket.org/2.0/repositories/jeroendr/meat-demo2/pipelines/ \<br/>
>   -d '<br/>
>   {<br/>
>     "target": {<br/>
>       "commit": {<br/>
>         "type": "commit", <br/>
>         "hash": "ce5b7431602f7cbba007062eeb55225c6e18e956"<br/>
>       }, <br/>
>       "ref_type": "branch", <br/>
>       "type": "pipeline_ref_target", <br/>
>       "ref_name": "master"<br/>
>     }<br/>
>   }'<br/>
> ```<br/>
> # Trigger a specific pipeline definition for a commit<br/>
> You can trigger a specific pipeline that is defined in your `bitbucket-pipelines.yml` file for a specific commit. <br/>
> In addition to the commit revision, you specify the type and pattern of the selector that identifies the pipeline definition. The resulting pipeline will then clone the repository and checkout the specified revision.<br/>
> <br/>
> ### Example<br/>
> <br/>
> ```<br/>
> $ curl -X POST -is -u username:password \<br/>
>   -H 'Content-Type: application/json' \<br/>
>  https://api.bitbucket.org/2.0/repositories/jeroendr/meat-demo2/pipelines/ \<br/>
>  -d '<br/>
>   {<br/>
>      "target": {<br/>
>       "commit": {<br/>
>          "hash":"a3c4e02c9a3755eccdc3764e6ea13facdf30f923",<br/>
>          "type":"commit"<br/>
>        },<br/>
>         "selector": {<br/>
>            "type":"custom",<br/>
>               "pattern":"Deploy to production"<br/>
>           },<br/>
>         "type":"pipeline_commit_target"<br/>
>    }<br/>
>   }'<br/>
> ```<br/>
> # Trigger a specific pipeline definition for a commit on a branch or tag<br/>
> You can trigger a specific pipeline that is defined in your `bitbucket-pipelines.yml` file for a specific commit in the context of a specified reference. <br/>
> In addition to the commit revision, you specify the type and pattern of the selector that identifies the pipeline definition, as well as the reference information. The resulting pipeline will then clone the repository a checkout the specified reference.<br/>
> <br/>
> ### Example<br/>
> <br/>
> ```<br/>
> $ curl -X POST -is -u username:password \<br/>
>   -H 'Content-Type: application/json' \<br/>
>  https://api.bitbucket.org/2.0/repositories/jeroendr/meat-demo2/pipelines/ \<br/>
>  -d '<br/>
>   {<br/>
>      "target": {<br/>
>       "commit": {<br/>
>          "hash":"a3c4e02c9a3755eccdc3764e6ea13facdf30f923",<br/>
>          "type":"commit"<br/>
>        },<br/>
>        "selector": {<br/>
>           "type": "custom",<br/>
>           "pattern": "Deploy to production"<br/>
>        },<br/>
>        "type": "pipeline_ref_target",<br/>
>        "ref_name": "master",<br/>
>        "ref_type": "branch"<br/>
>      }<br/>
>   }'<br/>
> ```

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Retrieve a specified pipeline

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `pipeline_uuid` - _required_ - The pipeline UUID.

### Find steps for the given pipeline.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `pipeline_uuid` - _required_ - The UUID of the pipeline.

### Retrieve a given step of a pipeline.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `pipeline_uuid` - _required_ - The UUID of the pipeline.
* `step_uuid` - _required_ - The UUID of the step.

### Retrieve the log file for a given step of a pipeline.<br/>
> <br/>
> This endpoint supports (and encourages!) the use of [HTTP Range requests](https://tools.ietf.org/html/rfc7233) to deal with potentially very large log files.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `pipeline_uuid` - _required_ - The UUID of the pipeline.
* `step_uuid` - _required_ - The UUID of the step.

### Signal the stop of a pipeline and all of its steps that not have completed yet.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `pipeline_uuid` - _required_ - The UUID of the pipeline.

### Retrieve the repository pipelines configuration.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Update the pipelines configuration for a repository.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Delete the repository SSH key pair.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Retrieve the repository SSH key pair excluding the SSH private key. The private key is a write only field and will never be exposed in the logs or the REST API.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Create or update the repository SSH key pair. The private key will be set as a default SSH identity in your build container.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Find repository level known hosts.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Create a repository level known host.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Delete a repository level known host.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `known_host_uuid` - _required_ - The UUID of the known host to delete.

### Retrieve a repository level known host.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `known_host_uuid` - _required_ - The UUID of the known host to retrieve.

### Update a repository level known host.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `known_host_uuid` - _required_ - The UUID of the known host to update.

### Find repository level variables.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Create a repository level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.

### Delete a repository level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `variable_uuid` - _required_ - The UUID of the variable to delete.

### Retrieve a repository level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `variable_uuid` - _required_ - The UUID of the variable to retrieve.

### Update a repository level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `repo_slug` - _required_ - The repository.
* `variable_uuid` - _required_ - The UUID of the variable to update.

### Returns a paginated list of all pull requests on the specified<br/>
> repository. By default only open pull requests are returned. This can<br/>
> be controlled using the `state` query parameter. To retrieve pull<br/>
> requests that are in one of multiple states, repeat the `state`<br/>
> parameter for each individual state.<br/>
> <br/>
> This endpoint also supports filtering and sorting of the results. See<br/>
> [filtering and sorting](../../../../meta/filtering) for more details.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.

* `state` - _optional_ - Only return pull requests that are in this state. This parameter can be repeated.
    Possible values: MERGED, SUPERSEDED, OPEN, DECLINED.

### Creates a new pull request.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.


### Returns a paginated list of the pull request's activity log.<br/>
> <br/>
> This includes comments that were made by the reviewers, updates and<br/>
> approvals.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.


### Returns the specified pull request.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the account,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.

* `pull_request_id` - _required_ - The id of the pull request.


### Mutates the specified pull request.<br/>
> <br/>
> This can be used to change the pull request's branches or description.<br/>
> <br/>
> Only open pull requests can be mutated.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.

* `pull_request_id` - _required_ - The id of the open pull request.


### Returns a paginated list of the pull request's activity log.<br/>
> <br/>
> This includes comments that were made by the reviewers, updates and<br/>
> approvals.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_ - This can either be the username or the UUID of the user,
surrounded by curly-braces, for example: `{user UUID}`.

* `repo_slug` - _required_ - This can either be the repository slug or the UUID of the repository,
surrounded by curly-braces, for example: `{repository UUID}`.

* `pull_request_id` - _required_ - The id of the pull request.


### Redact the authenticated user's approval of the specified pull<br/>
> request.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### Approve the specified pull request as the authenticated user.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### Returns a paginated list of the pull request's comments.<br/>
> <br/>
> This includes both global, inline comments and replies.<br/>
> <br/>
> The default sorting is oldest to newest and can be overridden with<br/>
> the `sort` query parameter.<br/>
> <br/>
> This endpoint also supports filtering and sorting of the results. See<br/>
> [filtering and sorting](../../../../../../meta/filtering) for more<br/>
> details.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### Returns a specific pull request comment.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `comment_id` - _required_
* `repo_slug` - _required_

### Returns a paginated list of the pull request's commits.<br/>
> <br/>
> These are the commits that are being merged into the destination<br/>
> branch when the pull requests gets accepted.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### Declines the pull request.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### get_repositories__username___repo_slug__pullrequests__pull_request_id__diff

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### Merges the pull request.

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### get_repositories__username___repo_slug__pullrequests__pull_request_id__patch

*Tags:* `pullrequests`

#### Input Parameters
* `username` - _required_
* `pull_request_id` - _required_
* `repo_slug` - _required_

### Returns all statuses (e.g. build results) for the given pull<br/>
> request.

*Tags:* `repositories` `pullrequests` `commitstatuses`

#### Input Parameters
* `pull_request_id` - _required_ - The pull request's id
* `pull_request_id` - _required_
* `repo_slug` - _required_

### get_repositories__username___repo_slug__refs

*Tags:* `refs`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### get_repositories__username___repo_slug__refs_branches

*Tags:* `refs`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### get_repositories__username___repo_slug__refs_branches__name_

*Tags:* `refs`

#### Input Parameters
* `username` - _required_
* `name` - _required_
* `repo_slug` - _required_

### get_repositories__username___repo_slug__refs_tags

*Tags:* `refs`

#### Input Parameters
* `username` - _required_ - 
The username for the owner of the repository. This can either be the
`username` of the owner or the `UUID` of the owner (surrounded by
curly-braces (`{}`)). Owners can be users or teams.

* `repo_slug` - _required_ - 
The repo slug for the repository.  This can either be the `repo_slug` of
the repository or the `UUID` of the repository (surrounded by
curly-braces (`{}`))


### Creates a new tag in the specified repository.<br/>
> <br/>
> The payload of the POST should consist of a JSON document that<br/>
> contains the name of the tag and the target hash.<br/>
> <br/>
> ```<br/>
> {<br/>
>     "name" : "new tag name",<br/>
>     "target" : {<br/>
>         "hash" : "target commit hash",<br/>
>     }<br/>
> }<br/>
> ```<br/>
> <br/>
> This endpoint does support using short hash prefixes for the commit<br/>
> hash, but it may return a 400 response if the provided prefix is<br/>
> ambiguous. Using a full commit hash is the preferred approach.

*Tags:* `refs`

#### Input Parameters
* `username` - _required_ - 
The username for the owner of the repository. This can either be the
`username` of the owner or the `UUID` of the owner (surrounded by
curly-braces (`{}`)). Owners can be users or teams.

* `repo_slug` - _required_ - 
The repo slug for the repository.  This can either be the `repo_slug` of
the repository or the `UUID` of the repository (surrounded by
curly-braces (`{}`))


### get_repositories__username___repo_slug__refs_tags__name_

*Tags:* `refs`

#### Input Parameters
* `username` - _required_
* `name` - _required_
* `repo_slug` - _required_

### get_repositories__username___repo_slug__src__node___path_

*Tags:* `source` `repositories`

#### Input Parameters
* `format` - _optional_ - Instead of returning the file's contents, return the (json) meta data for it.
    Possible values: meta.
* `node` - _required_
* `path` - _required_
* `repo_slug` - _required_

### Returns the versions that have been defined in the issue tracker.<br/>
> <br/>
> This resource is only available on repositories that have the issue<br/>
> tracker enabled.

*Tags:* `issue_tracker`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Returns the specified issue tracker version object.

*Tags:* `issue_tracker`

#### Input Parameters
* `version_id` - _required_ - The version's id
* `version_id` - _required_
* `repo_slug` - _required_

### Returns a paginated list of all the watchers on the specified<br/>
> repository.

*Tags:* `repositories`

#### Input Parameters
* `username` - _required_
* `repo_slug` - _required_

### Returns all snippets. Like pull requests, repositories and teams, the<br/>
> full set of snippets is defined by what the current user has access to.<br/>
> <br/>
> This includes all snippets owned by the current user, but also all snippets<br/>
> owned by any of the teams the user is a member of, or snippets by other<br/>
> users that the current user is either watching or has collaborated on (for<br/>
> instance by commenting on it).<br/>
> <br/>
> To limit the set of returned snippets, apply the<br/>
> `?role=[owner|contributor|member]` query parameter where the roles are<br/>
> defined as follows:<br/>
> <br/>
> * `owner`: all snippets owned by the current user<br/>
> * `contributor`: all snippets owned by, or watched by the current user<br/>
> * `member`: owned by the user, their teams, or watched by the current user<br/>
> <br/>
> When no role is specified, all public snippets are returned, as well as all<br/>
> privately owned snippets watched or commented on.<br/>
> <br/>
> The returned response is a normal paginated JSON list. This endpoint<br/>
> only supports `application/json` responses and no<br/>
> `multipart/form-data` or `multipart/related`. As a result, it is not<br/>
> possible to include the file contents.

*Tags:* `snippets`

#### Input Parameters
* `role` - _optional_ - Filter down the result based on the authenticated user's role (`owner`, `contributor`, or `member`).
    Possible values: owner, contributor, member.

### Creates a new snippet under the authenticated user's account.<br/>
> <br/>
> Snippets can contain multiple files. Both text and binary files are<br/>
> supported.<br/>
> <br/>
> The simplest way to create a new snippet from a local file:<br/>
> <br/>
>     $ curl -u username:password -X POST https://api.bitbucket.org/2.0/snippets               -F file=@image.png<br/>
> <br/>
> Creating snippets through curl has a few limitations and so let's look<br/>
> at a more complicated scenario.<br/>
> <br/>
> Snippets are created with a multipart POST. Both `multipart/form-data`<br/>
> and `multipart/related` are supported. Both allow the creation of<br/>
> snippets with both meta data (title, etc), as well as multiple text<br/>
> and binary files.<br/>
> <br/>
> The main difference is that `multipart/related` can use rich encoding<br/>
> for the meta data (currently JSON).<br/>
> <br/>
> <br/>
> multipart/related (RFC-2387)<br/>
> ----------------------------<br/>
> <br/>
> This is the most advanced and efficient way to create a paste.<br/>
> <br/>
>     POST /2.0/snippets/evzijst HTTP/1.1<br/>
>     Content-Length: 1188<br/>
>     Content-Type: multipart/related; start="snippet"; boundary="===============1438169132528273974=="<br/>
>     MIME-Version: 1.0<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: application/json; charset="utf-8"<br/>
>     MIME-Version: 1.0<br/>
>     Content-ID: snippet<br/>
> <br/>
>     {<br/>
>       "title": "My snippet",<br/>
>       "is_private": true,<br/>
>       "scm": "hg",<br/>
>       "files": {<br/>
>           "foo.txt": {},<br/>
>           "image.png": {}<br/>
>         }<br/>
>     }<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: text/plain; charset="us-ascii"<br/>
>     MIME-Version: 1.0<br/>
>     Content-Transfer-Encoding: 7bit<br/>
>     Content-ID: "foo.txt"<br/>
>     Content-Disposition: attachment; filename="foo.txt"<br/>
> <br/>
>     foo<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: image/png<br/>
>     MIME-Version: 1.0<br/>
>     Content-Transfer-Encoding: base64<br/>
>     Content-ID: "image.png"<br/>
>     Content-Disposition: attachment; filename="image.png"<br/>
> <br/>
>     iVBORw0KGgoAAAANSUhEUgAAABQAAAAoCAYAAAD+MdrbAAABD0lEQVR4Ae3VMUoDQRTG8ccUaW2m<br/>
>     TKONFxArJYJamCvkCnZTaa+VnQdJSBFl2SMsLFrEWNjZBZs0JgiL/+KrhhVmJRbCLPx4O+/DT2TB<br/>
>     cbblJxf+UWFVVRNsEGAtgvJxnLm2H+A5RQ93uIl+3632PZyl/skjfOn9Gvdwmlcw5aPUwimG+NT5<br/>
>     EnNN036IaZePUuIcK533NVfal7/5yjWeot2z9ta1cAczHEf7I+3J0ws9Cgx0fsOFpmlfwKcWPuBQ<br/>
>     73Oc4FHzBaZ8llq4q1mr5B2mOUCt815qYR8eB1hG2VJ7j35q4RofaH7IG+Xrf/PfJhfmwtfFYoIN<br/>
>     AqxFUD6OMxcvkO+UfKfkOyXfKdsv/AYCHMLVkHAFWgAAAABJRU5ErkJggg==<br/>
>     --===============1438169132528273974==--<br/>
> <br/>
> The request contains multiple parts and is structured as follows.<br/>
> <br/>
> The first part is the JSON document that describes the snippet's<br/>
> properties or meta data. It either has to be the first part, or the<br/>
> request's `Content-Type` header must contain the `start` parameter to<br/>
> point to it.<br/>
> <br/>
> The remaining parts are the files of which there can be zero or more.<br/>
> Each file part should contain the `Content-ID` MIME header through<br/>
> which the JSON meta data's `files` element addresses it. The value<br/>
> should be the name of the file.<br/>
> <br/>
> `Content-Disposition` is an optional MIME header. The header's<br/>
> optional `filename` parameter can be used to specify the file name<br/>
> that Bitbucket should use when writing the file to disk. When present,<br/>
> `filename` takes precedence over the value of `Content-ID`.<br/>
> <br/>
> When the JSON body omits the `files` element, the remaining parts are<br/>
> not ignored. Instead, each file is added to the new snippet as if its<br/>
> name was explicitly linked (the use of the `files` elements is<br/>
> mandatory for some operations like deleting or renaming files).<br/>
> <br/>
> <br/>
> multipart/form-data<br/>
> -------------------<br/>
> <br/>
> The use of JSON for the snippet's meta data is optional. Meta data can<br/>
> also be supplied as regular form fields in a more conventional<br/>
> `multipart/form-data` request:<br/>
> <br/>
>     $ curl -X POST -u credentials https://api.bitbucket.org/2.0/snippets               -F title="My snippet"               -F file=@foo.txt -F file=@image.png<br/>
> <br/>
>     POST /2.0/snippets HTTP/1.1<br/>
>     Content-Length: 951<br/>
>     Content-Type: multipart/form-data; boundary=----------------------------63a4b224c59f<br/>
> <br/>
>     ------------------------------63a4b224c59f<br/>
>     Content-Disposition: form-data; name="file"; filename="foo.txt"<br/>
>     Content-Type: text/plain<br/>
> <br/>
>     foo<br/>
> <br/>
>     ------------------------------63a4b224c59f<br/>
>     Content-Disposition: form-data; name="file"; filename="image.png"<br/>
>     Content-Type: application/octet-stream<br/>
> <br/>
>     ?PNG<br/>
> <br/>
>     IHDR?1??I.....<br/>
>     ------------------------------63a4b224c59f<br/>
>     Content-Disposition: form-data; name="title"<br/>
> <br/>
>     My snippet<br/>
>     ------------------------------63a4b224c59f--<br/>
> <br/>
> Here the meta data properties are included as flat, top-level form<br/>
> fields. The file attachments use the `file` field name. To attach<br/>
> multiple files, simply repeat the field.<br/>
> <br/>
> The advantage of `multipart/form-data` over `multipart/related` is<br/>
> that it can be easier to build clients.<br/>
> <br/>
> Essentially all properties are optional, `title` and `files` included.<br/>
> <br/>
> <br/>
> Sharing and Visibility<br/>
> ----------------------<br/>
> <br/>
> Snippets can be either public (visible to anyone on Bitbucket, as well<br/>
> as anonymous users), or private (visible only to the owner, creator<br/>
> and members of the team in case the snippet is owned by a team). This<br/>
> is controlled through the snippet's `is_private` element:<br/>
> <br/>
> * **is_private=false** -- everyone, including anonymous users can view<br/>
>   the snippet<br/>
> * **is_private=true** -- only the owner and team members (for team<br/>
>   snippets) can view it<br/>
> <br/>
> To create the snippet under a team account, just append the team name<br/>
> to the URL (see `/2.0/snippets/{username}`).

*Tags:* `snippets`

### Identical to `/snippets`, except that the result is further filtered<br/>
> by the snippet owner and only those that are owned by `{username}` are<br/>
> returned.

*Tags:* `snippets`

#### Input Parameters
* `role` - _optional_ - Filter down the result based on the authenticated user's role (`owner`, `contributor`, or `member`).
    Possible values: owner, contributor, member.
* `username` - _required_ - Limits the result to snippets owned by this user.

### Identical to `/snippets`, except that the new snippet will be<br/>
> created under the account specified in the path parameter `{username}`.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_

### Deletes a snippet and returns an empty response.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet's id.
* `encoded_id` - _required_

### Retrieves a single snippet.<br/>
> <br/>
> Snippets support multiple content types:<br/>
> <br/>
> * application/json<br/>
> * multipart/related<br/>
> * multipart/form-data<br/>
> <br/>
> <br/>
> application/json<br/>
> ----------------<br/>
> <br/>
> The default content type of the response is `application/json`.<br/>
> Since JSON is always `utf-8`, it cannot reliably contain file contents<br/>
> for files that are not text. Therefore, JSON snippet documents only<br/>
> contain the filename and links to the file contents.<br/>
> <br/>
> This means that in order to retrieve all parts of a snippet, N+1<br/>
> requests need to be made (where N is the number of files in the<br/>
> snippet).<br/>
> <br/>
> <br/>
> multipart/related<br/>
> -----------------<br/>
> <br/>
> To retrieve an entire snippet in a single response, use the<br/>
> `Accept: multipart/related` HTTP request header.<br/>
> <br/>
>     $ curl -H "Accept: multipart/related" https://api.bitbucket.org/2.0/snippets/evzijst/1<br/>
> <br/>
> Response:<br/>
> <br/>
>     HTTP/1.1 200 OK<br/>
>     Content-Length: 2214<br/>
>     Content-Type: multipart/related; start="snippet"; boundary="===============1438169132528273974=="<br/>
>     MIME-Version: 1.0<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: application/json; charset="utf-8"<br/>
>     MIME-Version: 1.0<br/>
>     Content-ID: snippet<br/>
> <br/>
>     {<br/>
>       "links": {<br/>
>         "self": {<br/>
>           "href": "https://api.bitbucket.org/2.0/snippets/evzijst/kypj"<br/>
>         },<br/>
>         "html": {<br/>
>           "href": "https://bitbucket.org/snippets/evzijst/kypj"<br/>
>         },<br/>
>         "comments": {<br/>
>           "href": "https://api.bitbucket.org/2.0/snippets/evzijst/kypj/comments"<br/>
>         },<br/>
>         "watchers": {<br/>
>           "href": "https://api.bitbucket.org/2.0/snippets/evzijst/kypj/watchers"<br/>
>         },<br/>
>         "commits": {<br/>
>           "href": "https://api.bitbucket.org/2.0/snippets/evzijst/kypj/commits"<br/>
>         }<br/>
>       },<br/>
>       "id": kypj,<br/>
>       "title": "My snippet",<br/>
>       "created_on": "2014-12-29T22:22:04.790331+00:00",<br/>
>       "updated_on": "2014-12-29T22:22:04.790331+00:00",<br/>
>       "is_private": false,<br/>
>       "files": {<br/>
>         "foo.txt": {<br/>
>           "links": {<br/>
>             "self": {<br/>
>               "href": "https://api.bitbucket.org/2.0/snippets/evzijst/kypj/files/367ab19/foo.txt"<br/>
>             },<br/>
>             "html": {<br/>
>               "href": "https://bitbucket.org/snippets/evzijst/kypj#file-foo.txt"<br/>
>             }<br/>
>           }<br/>
>         },<br/>
>         "image.png": {<br/>
>           "links": {<br/>
>             "self": {<br/>
>               "href": "https://api.bitbucket.org/2.0/snippets/evzijst/kypj/files/367ab19/image.png"<br/>
>             },<br/>
>             "html": {<br/>
>               "href": "https://bitbucket.org/snippets/evzijst/kypj#file-image.png"<br/>
>             }<br/>
>           }<br/>
>         }<br/>
>       ],<br/>
>       "owner": {<br/>
>         "username": "evzijst",<br/>
>         "display_name": "Erik van Zijst",<br/>
>         "uuid": "{d301aafa-d676-4ee0-88be-962be7417567}",<br/>
>         "links": {<br/>
>           "self": {<br/>
>             "href": "https://api.bitbucket.org/2.0/users/evzijst"<br/>
>           },<br/>
>           "html": {<br/>
>             "href": "https://bitbucket.org/evzijst"<br/>
>           },<br/>
>           "avatar": {<br/>
>             "href": "https://bitbucket-staging-assetroot.s3.amazonaws.com/c/photos/2013/Jul/31/erik-avatar-725122544-0_avatar.png"<br/>
>           }<br/>
>         }<br/>
>       },<br/>
>       "creator": {<br/>
>         "username": "evzijst",<br/>
>         "display_name": "Erik van Zijst",<br/>
>         "uuid": "{d301aafa-d676-4ee0-88be-962be7417567}",<br/>
>         "links": {<br/>
>           "self": {<br/>
>             "href": "https://api.bitbucket.org/2.0/users/evzijst"<br/>
>           },<br/>
>           "html": {<br/>
>             "href": "https://bitbucket.org/evzijst"<br/>
>           },<br/>
>           "avatar": {<br/>
>             "href": "https://bitbucket-staging-assetroot.s3.amazonaws.com/c/photos/2013/Jul/31/erik-avatar-725122544-0_avatar.png"<br/>
>           }<br/>
>         }<br/>
>       }<br/>
>     }<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: text/plain; charset="us-ascii"<br/>
>     MIME-Version: 1.0<br/>
>     Content-Transfer-Encoding: 7bit<br/>
>     Content-ID: "foo.txt"<br/>
>     Content-Disposition: attachment; filename="foo.txt"<br/>
> <br/>
>     foo<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: image/png<br/>
>     MIME-Version: 1.0<br/>
>     Content-Transfer-Encoding: base64<br/>
>     Content-ID: "image.png"<br/>
>     Content-Disposition: attachment; filename="image.png"<br/>
> <br/>
>     iVBORw0KGgoAAAANSUhEUgAAABQAAAAoCAYAAAD+MdrbAAABD0lEQVR4Ae3VMUoDQRTG8ccUaW2m<br/>
>     TKONFxArJYJamCvkCnZTaa+VnQdJSBFl2SMsLFrEWNjZBZs0JgiL/+KrhhVmJRbCLPx4O+/DT2TB<br/>
>     cbblJxf+UWFVVRNsEGAtgvJxnLm2H+A5RQ93uIl+3632PZyl/skjfOn9Gvdwmlcw5aPUwimG+NT5<br/>
>     EnNN036IaZePUuIcK533NVfal7/5yjWeot2z9ta1cAczHEf7I+3J0ws9Cgx0fsOFpmlfwKcWPuBQ<br/>
>     73Oc4FHzBaZ8llq4q1mr5B2mOUCt815qYR8eB1hG2VJ7j35q4RofaH7IG+Xrf/PfJhfmwtfFYoIN<br/>
>     AqxFUD6OMxcvkO+UfKfkOyXfKdsv/AYCHMLVkHAFWgAAAABJRU5ErkJggg==<br/>
>     --===============1438169132528273974==--<br/>
> <br/>
> multipart/form-data<br/>
> -------------------<br/>
> <br/>
> As with creating new snippets, `multipart/form-data` can be used as an<br/>
> alternative to `multipart/related`. However, the inherently flat<br/>
> structure of form-data means that only basic, root-level properties<br/>
> can be returned, while nested elements like `links` are omitted:<br/>
> <br/>
>     $ curl -H "Accept: multipart/form-data" https://api.bitbucket.org/2.0/snippets/evzijst/kypj<br/>
> <br/>
> Response:<br/>
> <br/>
>     HTTP/1.1 200 OK<br/>
>     Content-Length: 951<br/>
>     Content-Type: multipart/form-data; boundary=----------------------------63a4b224c59f<br/>
> <br/>
>     ------------------------------63a4b224c59f<br/>
>     Content-Disposition: form-data; name="title"<br/>
>     Content-Type: text/plain; charset="utf-8"<br/>
> <br/>
>     My snippet<br/>
>     ------------------------------63a4b224c59f--<br/>
>     Content-Disposition: attachment; name="file"; filename="foo.txt"<br/>
>     Content-Type: text/plain<br/>
> <br/>
>     foo<br/>
> <br/>
>     ------------------------------63a4b224c59f<br/>
>     Content-Disposition: attachment; name="file"; filename="image.png"<br/>
>     Content-Transfer-Encoding: base64<br/>
>     Content-Type: application/octet-stream<br/>
> <br/>
>     iVBORw0KGgoAAAANSUhEUgAAABQAAAAoCAYAAAD+MdrbAAABD0lEQVR4Ae3VMUoDQRTG8ccUaW2m<br/>
>     TKONFxArJYJamCvkCnZTaa+VnQdJSBFl2SMsLFrEWNjZBZs0JgiL/+KrhhVmJRbCLPx4O+/DT2TB<br/>
>     cbblJxf+UWFVVRNsEGAtgvJxnLm2H+A5RQ93uIl+3632PZyl/skjfOn9Gvdwmlcw5aPUwimG+NT5<br/>
>     EnNN036IaZePUuIcK533NVfal7/5yjWeot2z9ta1cAczHEf7I+3J0ws9Cgx0fsOFpmlfwKcWPuBQ<br/>
>     73Oc4FHzBaZ8llq4q1mr5B2mOUCt815qYR8eB1hG2VJ7j35q4RofaH7IG+Xrf/PfJhfmwtfFYoIN<br/>
>     AqxFUD6OMxcvkO+UfKfkOyXfKdsv/AYCHMLVkHAFWgAAAABJRU5ErkJggg==<br/>
>     ------------------------------5957323a6b76--

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet's id.
* `encoded_id` - _required_

### Used to update a snippet. Use this to add and delete files and to<br/>
> change a snippet's title.<br/>
> <br/>
> To update a snippet, one can either PUT a full snapshot, or only the<br/>
> parts that need to be changed.<br/>
> <br/>
> The contract for PUT on this API is that properties missing from the<br/>
> request remain untouched so that snippets can be efficiently<br/>
> manipulated with differential payloads.<br/>
> <br/>
> To delete a property (e.g. the title, or a file), include its name in<br/>
> the request, but omit its value (use `null`).<br/>
> <br/>
> As in Git, explicit renaming of files is not supported. Instead, to<br/>
> rename a file, delete it and add it again under another name. This can<br/>
> be done atomically in a single request. Rename detection is left to<br/>
> the SCM.<br/>
> <br/>
> PUT supports three different content types for both request and<br/>
> response bodies:<br/>
> <br/>
> * `application/json`<br/>
> * `multipart/related`<br/>
> * `multipart/form-data`<br/>
> <br/>
> The content type used for the request body can be different than that<br/>
> used for the response. Content types are specified using standard HTTP<br/>
> headers.<br/>
> <br/>
> Use the `Content-Type` and `Accept` headers to select the desired<br/>
> request and response format.<br/>
> <br/>
> <br/>
> application/json<br/>
> ----------------<br/>
> <br/>
> As with creation and retrieval, the content type determines what<br/>
> properties can be manipulated. `application/json` does not support<br/>
> file contents and is therefore limited to a snippet's meta data.<br/>
> <br/>
> To update the title, without changing any of its files:<br/>
> <br/>
>     $ curl -X POST -H "Content-Type: application/json" https://api.bitbucket.org/2.0/snippets/evzijst/kypj             -d '{"title": "Updated title"}'<br/>
> <br/>
> <br/>
> To delete the title:<br/>
> <br/>
>     $ curl -X POST -H "Content-Type: application/json" https://api.bitbucket.org/2.0/snippets/evzijst/kypj             -d '{"title": null}'<br/>
> <br/>
> Not all parts of a snippet can be manipulated. The owner and creator<br/>
> for instance are immutable.<br/>
> <br/>
> <br/>
> multipart/related<br/>
> -----------------<br/>
> <br/>
> `multipart/related` can be used to manipulate all of a snippet's<br/>
> properties. The body is identical to a POST. properties omitted from<br/>
> the request are left unchanged. Since the `start` part contains JSON,<br/>
> the mechanism for manipulating the snippet's meta data is identical<br/>
> to `application/json` requests.<br/>
> <br/>
> To update one of a snippet's file contents, while also changing its<br/>
> title:<br/>
> <br/>
>     PUT /2.0/snippets/evzijst/kypj HTTP/1.1<br/>
>     Content-Length: 288<br/>
>     Content-Type: multipart/related; start="snippet"; boundary="===============1438169132528273974=="<br/>
>     MIME-Version: 1.0<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: application/json; charset="utf-8"<br/>
>     MIME-Version: 1.0<br/>
>     Content-ID: snippet<br/>
> <br/>
>     {<br/>
>       "title": "My updated snippet",<br/>
>       "files": {<br/>
>           "foo.txt": {}<br/>
>         }<br/>
>     }<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: text/plain; charset="us-ascii"<br/>
>     MIME-Version: 1.0<br/>
>     Content-Transfer-Encoding: 7bit<br/>
>     Content-ID: "foo.txt"<br/>
>     Content-Disposition: attachment; filename="foo.txt"<br/>
> <br/>
>     Updated file contents.<br/>
> <br/>
>     --===============1438169132528273974==--<br/>
> <br/>
> Here only the parts that are changed are included in the body. The<br/>
> other files remain untouched.<br/>
> <br/>
> Note the use of the `files` list in the JSON part. This list contains<br/>
> the files that are being manipulated. This list should have<br/>
> corresponding multiparts in the request that contain the new contents<br/>
> of these files.<br/>
> <br/>
> If a filename in the `files` list does not have a corresponding part,<br/>
> it will be deleted from the snippet, as shown below:<br/>
> <br/>
>     PUT /2.0/snippets/evzijst/kypj HTTP/1.1<br/>
>     Content-Length: 188<br/>
>     Content-Type: multipart/related; start="snippet"; boundary="===============1438169132528273974=="<br/>
>     MIME-Version: 1.0<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: application/json; charset="utf-8"<br/>
>     MIME-Version: 1.0<br/>
>     Content-ID: snippet<br/>
> <br/>
>     {<br/>
>       "files": {<br/>
>         "image.png": {}<br/>
>       }<br/>
>     }<br/>
> <br/>
>     --===============1438169132528273974==--<br/>
> <br/>
> To simulate a rename, delete a file and add the same file under<br/>
> another name:<br/>
> <br/>
>     PUT /2.0/snippets/evzijst/kypj HTTP/1.1<br/>
>     Content-Length: 212<br/>
>     Content-Type: multipart/related; start="snippet"; boundary="===============1438169132528273974=="<br/>
>     MIME-Version: 1.0<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: application/json; charset="utf-8"<br/>
>     MIME-Version: 1.0<br/>
>     Content-ID: snippet<br/>
> <br/>
>     {<br/>
>         "files": {<br/>
>           "foo.txt": {},<br/>
>           "bar.txt": {}<br/>
>         }<br/>
>     }<br/>
> <br/>
>     --===============1438169132528273974==<br/>
>     Content-Type: text/plain; charset="us-ascii"<br/>
>     MIME-Version: 1.0<br/>
>     Content-Transfer-Encoding: 7bit<br/>
>     Content-ID: "bar.txt"<br/>
>     Content-Disposition: attachment; filename="bar.txt"<br/>
> <br/>
>     foo<br/>
> <br/>
>     --===============1438169132528273974==--<br/>
> <br/>
> <br/>
> multipart/form-data<br/>
> -----------------<br/>
> <br/>
> Again, one can also use `multipart/form-data` to manipulate file<br/>
> contents and meta data atomically.<br/>
> <br/>
>     $ curl -X PUT http://localhost:12345/2.0/snippets/evzijst/kypj             -F title="My updated snippet" -F file=@foo.txt<br/>
> <br/>
>     PUT /2.0/snippets/evzijst/kypj HTTP/1.1<br/>
>     Content-Length: 351<br/>
>     Content-Type: multipart/form-data; boundary=----------------------------63a4b224c59f<br/>
> <br/>
>     ------------------------------63a4b224c59f<br/>
>     Content-Disposition: form-data; name="file"; filename="foo.txt"<br/>
>     Content-Type: text/plain<br/>
> <br/>
>     foo<br/>
> <br/>
>     ------------------------------63a4b224c59f<br/>
>     Content-Disposition: form-data; name="title"<br/>
> <br/>
>     My updated snippet<br/>
>     ------------------------------63a4b224c59f<br/>
> <br/>
> To delete a file, omit its contents while including its name in the<br/>
> `files` field:<br/>
> <br/>
>     $ curl -X PUT https://api.bitbucket.org/2.0/snippets/evzijst/kypj -F files=image.png<br/>
> <br/>
>     PUT /2.0/snippets/evzijst/kypj HTTP/1.1<br/>
>     Content-Length: 149<br/>
>     Content-Type: multipart/form-data; boundary=----------------------------ef8871065a86<br/>
> <br/>
>     ------------------------------ef8871065a86<br/>
>     Content-Disposition: form-data; name="files"<br/>
> <br/>
>     image.png<br/>
>     ------------------------------ef8871065a86--<br/>
> <br/>
> The explicit use of the `files` element in `multipart/related` and<br/>
> `multipart/form-data` is only required when deleting files.<br/>
> The default mode of operation is for file parts to be processed,<br/>
> regardless of whether or not they are listed in `files`, as a<br/>
> convenience to the client.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet's id.
* `encoded_id` - _required_

### Used to retrieve a paginated list of all comments for a specific<br/>
> snippet.<br/>
> <br/>
> This resource works identical to commit and pull request comments.<br/>
> <br/>
> The default sorting is oldest to newest and can be overridden with<br/>
> the `sort` query parameter.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `encoded_id` - _required_

### Creates a new comment.<br/>
> <br/>
> The only required field in the body is `content.raw`.<br/>
> <br/>
> To create a threaded reply to an existing comment, include `parent.id`.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `encoded_id` - _required_

### Deletes a snippet comment.<br/>
> <br/>
> Comments can only be removed by their author.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `comment_id` - _required_
* `encoded_id` - _required_

### Returns the specific snippet comment.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `comment_id` - _required_
* `encoded_id` - _required_

### Updates a comment.<br/>
> <br/>
> Comments can only be updated by their author.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `comment_id` - _required_
* `encoded_id` - _required_

### Returns the changes (commits) made on this snippet.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `encoded_id` - _required_

### get_snippets__username___encoded_id__commits__revision_

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `encoded_id` - _required_
* `revision` - _required_

### Used to stop watching a specific snippet. Returns 204 (No Content)<br/>
> to indicate success.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet id.
* `encoded_id` - _required_

### Used to check if the current user is watching a specific snippet.<br/>
> <br/>
> Returns 204 (No Content) if the user is watching the snippet and 404 if<br/>
> not.<br/>
> <br/>
> Hitting this endpoint anonymously always returns a 404.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet id.
* `encoded_id` - _required_

### Used to start watching a specific snippet. Returns 204 (No Content).

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet id.
* `encoded_id` - _required_

### Returns a paginated list of all users watching a specific snippet.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet id.
* `encoded_id` - _required_

### Deletes the snippet.<br/>
> <br/>
> Note that this only works for versioned URLs that point to the latest<br/>
> commit of the snippet. Pointing to an older commit results in a 405<br/>
> status code.<br/>
> <br/>
> To delete a snippet, regardless of whether or not concurrent changes<br/>
> are being made to it, use `DELETE /snippets/{encoded_id}` instead.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet's id.
* `node_id` - _required_
* `encoded_id` - _required_

### Identical to `GET /snippets/encoded_id`, except that this endpoint<br/>
> can be used to retrieve the contents of the snippet as it was at an<br/>
> older revision, while `/snippets/encoded_id` always returns the<br/>
> snippet's current revision.<br/>
> <br/>
> Note that only the snippet's file contents are versioned, not its<br/>
> meta data properties like the title.<br/>
> <br/>
> Other than that, the two endpoints are identical in behavior.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet's id.
* `node_id` - _required_ - A commit revision (SHA1).
* `encoded_id` - _required_

### Identical to `UPDATE /snippets/encoded_id`, except that this endpoint<br/>
> takes an explicit commit revision. Only the snippet's "HEAD"/"tip"<br/>
> (most recent) version can be updated and requests on all other,<br/>
> older revisions fail by returning a 405 status.<br/>
> <br/>
> Usage of this endpoint over the unrestricted `/snippets/encoded_id`<br/>
> could be desired if the caller wants to be sure no concurrent<br/>
> modifications have taken place between the moment of the UPDATE<br/>
> request and the original GET.<br/>
> <br/>
> This can be considered a so-called "Compare And Swap", or CAS<br/>
> operation.<br/>
> <br/>
> Other than that, the two endpoints are identical in behavior.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet's id.
* `node_id` - _required_ - A commit revision (SHA1).
* `encoded_id` - _required_

### Retrieves the raw contents of a specific file in the snippet. The<br/>
> `Content-Disposition` header will be "attachment" to avoid issues with<br/>
> malevolent executable files.<br/>
> <br/>
> The file's mime type is derived from its filename and returned in the<br/>
> `Content-Type` header.<br/>
> <br/>
> Note that for text files, no character encoding is included as part of<br/>
> the content type.

*Tags:* `snippets`

#### Input Parameters
* `username` - _required_
* `path` - _required_
* `node_id` - _required_
* `encoded_id` - _required_

### Returns the diff of the specified commit against its first parent.<br/>
> <br/>
> Note that this resource is different in functionality from the `patch`<br/>
> resource.<br/>
> <br/>
> The differences between a diff and a patch are:<br/>
> <br/>
> * patches have a commit header with the username, message, etc<br/>
> * diffs support the optional `path=foo/bar.py` query param to filter the<br/>
>   diff to just that one file diff (not supported for patches)<br/>
> * for a merge, the diff will show the diff between the merge commit and<br/>
>   its first parent (identical to how PRs work), while patch returns a<br/>
>   response containing separate patches for each commit on the second<br/>
>   parent's ancestry, up to the oldest common ancestor (identical to<br/>
>   its reachability).<br/>
> <br/>
> Note that the character encoding of the contents of the diff is<br/>
> unspecified as Git and Mercurial do not track this, making it hard for<br/>
> Bitbucket to reliably determine this.

*Tags:* `snippets`

#### Input Parameters
* `path` - _optional_ - When used, only one the diff of the specified file will be returned.
* `encoded_id` - _required_ - The snippet id.
* `revision` - _required_ - A revspec expression. This can simply be a commit SHA1, a ref name, or a compare expression like `staging..production`.

### Returns the patch of the specified commit against its first<br/>
> parent.<br/>
> <br/>
> Note that this resource is different in functionality from the `diff`<br/>
> resource.<br/>
> <br/>
> The differences between a diff and a patch are:<br/>
> <br/>
> * patches have a commit header with the username, message, etc<br/>
> * diffs support the optional `path=foo/bar.py` query param to filter the<br/>
>   diff to just that one file diff (not supported for patches)<br/>
> * for a merge, the diff will show the diff between the merge commit and<br/>
>   its first parent (identical to how PRs work), while patch returns a<br/>
>   response containing separate patches for each commit on the second<br/>
>   parent's ancestry, up to the oldest common ancestor (identical to<br/>
>   its reachability).<br/>
> <br/>
> Note that the character encoding of the contents of the patch is<br/>
> unspecified as Git and Mercurial do not track this, making it hard for<br/>
> Bitbucket to reliably determine this.

*Tags:* `snippets`

#### Input Parameters
* `encoded_id` - _required_ - The snippet id.
* `revision` - _required_ - A revspec expression. This can simply be a commit SHA1, a ref name, or a compare expression like `staging..production`.
* `revision` - _required_

### Returns all the teams that the authenticated user is associated<br/>
> with.

*Tags:* `teams`

#### Input Parameters
* `role` - _optional_ - 
Filters the teams based on the authenticated user's role on each team.

* **member**: returns a list of all the teams which the caller is a member of
  at least one team group or repository owned by the team
* **contributor**: returns a list of teams which the caller has write access
  to at least one repository owned by the team
* **admin**: returns a list teams which the caller has team administrator access

    Possible values: admin, contributor, member.

### get_teams__owner__projects_

*Tags:* `projects`

#### Input Parameters
* `owner` - _required_ - The team which owns the project. This can either be the `username` of
the team or the `UUID` of the team (surrounded by curly-braces (`{}`)).


### Creates a new project.<br/>
> <br/>
> Note that the avatar has to be embedded as either a data-url<br/>
> or a URL to an external image as shown in the examples below:<br/>
> <br/>
> ```<br/>
> $ body=$(cat << EOF<br/>
> {<br/>
>     "name": "Mars Project",<br/>
>     "key": "MARS",<br/>
>     "description": "Software for colonizing mars.",<br/>
>     "links": {<br/>
>         "avatar": {<br/>
>             "href": "data:image/gif;base64,R0lGODlhEAAQAMQAAORHHOVSKudfOulrSOp3WOyDZu6QdvCchPGolfO0o/..."<br/>
>         }<br/>
>     },<br/>
>     "is_private": false<br/>
> }<br/>
> EOF<br/>
> )<br/>
> $ curl -H "Content-Type: application/json" \<br/>
>        -X POST \<br/>
>        -d "$body" \<br/>
>        https://api.bitbucket.org/2.0/teams/teams-in-space/projects/ | jq .<br/>
> {<br/>
>   // Serialized project document<br/>
> }<br/>
> ```<br/>
> <br/>
> or even:<br/>
> <br/>
> ```<br/>
> $ body=$(cat << EOF<br/>
> {<br/>
>     "name": "Mars Project",<br/>
>     "key": "MARS",<br/>
>     "description": "Software for colonizing mars.",<br/>
>     "links": {<br/>
>         "avatar": {<br/>
>             "href": "http://i.imgur.com/72tRx4w.gif"<br/>
>         }<br/>
>     },<br/>
>     "is_private": false<br/>
> }<br/>
> EOF<br/>
> )<br/>
> $ curl -H "Content-Type: application/json" \<br/>
>        -X POST \<br/>
>        -d "$body" \<br/>
>        https://api.bitbucket.org/2.0/teams/teams-in-space/projects/ | jq .<br/>
> {<br/>
>   // Serialized project document<br/>
> }<br/>
> ```

*Tags:* `projects`

#### Input Parameters
* `owner` - _required_ - The team which owns the project. This can either be the `username` of
the team or the `UUID` of the team (surrounded by curly-braces (`{}`)).


### delete_teams__owner__projects__project_key_

*Tags:* `projects`

#### Input Parameters
* `owner` - _required_ - The team which owns the project. This can either be the `username` of
the team or the `UUID` of the team (surrounded by curly-braces (`{}`)).

* `project_key` - _required_ - The project in question. This can either be the actual `key` assigned
to the project or the `UUID` (surrounded by curly-braces (`{}`)).


### get_teams__owner__projects__project_key_

*Tags:* `projects`

#### Input Parameters
* `owner` - _required_ - The team which owns the project. This can either be the `username` of
the team or the `UUID` of the team (surrounded by curly-braces (`{}`)).

* `project_key` - _required_ - The project in question. This can either be the actual `key` assigned
to the project or the `UUID` (surrounded by curly-braces (`{}`)).


### Since this endpoint can be used to both update and to create a<br/>
> project, the request body depends on the intent.<br/>
> <br/>
> ### Creation<br/>
> <br/>
> See the POST documentation for the project collection for an<br/>
> example of the request body.<br/>
> <br/>
> Note: The `key` should not be specified in the body of request<br/>
> (since it is already present in the URL). The `name` is required,<br/>
> everything else is optional.<br/>
> <br/>
> ### Update<br/>
> <br/>
> See the POST documentation for the project collection for an<br/>
> example of the request body.<br/>
> <br/>
> Note: The key is not required in the body (since it is already in<br/>
> the URL). The key may be specified in the body, if the intent is<br/>
> to change the key itself. In such a scenario, the location of the<br/>
> project is changed and is returned in the `Location` header of the<br/>
> response.

*Tags:* `projects`

#### Input Parameters
* `owner` - _required_ - The team which owns the project. This can either be the `username` of
the team or the `UUID` of the team (surrounded by curly-braces (`{}`)).

* `project_key` - _required_ - The project in question. This can either be the actual `key` assigned
to the project or the `UUID` (surrounded by curly-braces (`{}`)).


### Gets the public information associated with a team.<br/>
> <br/>
> If the team's profile is private, `location`, `website` and<br/>
> `created_on` elements are omitted.

*Tags:* `teams`

#### Input Parameters
* `username` - _required_ - The team's username or UUID.

### Returns the list of accounts that are following this team.

*Tags:* `teams`

#### Input Parameters
* `username` - _required_ - The team's username

### Returns the list of accounts this team is following.

*Tags:* `teams`

#### Input Parameters
* `username` - _required_ - The team's username

### Returns a paginated list of webhooks installed on this team.

*Tags:* `teams` `webhooks`

#### Input Parameters
* `username` - _required_

### Creates a new webhook on the specified team.<br/>
> <br/>
> Team webhooks are fired for events from all repositories belonging to<br/>
> that team account.<br/>
> <br/>
> Note that only admins can install webhooks on teams.

*Tags:* `teams` `webhooks`

#### Input Parameters
* `username` - _required_

### Deletes the specified webhook subscription from the given team<br/>
> account.

*Tags:* `teams` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id
* `uid` - _required_

### Returns the webhook with the specified id installed on the given<br/>
> team account.

*Tags:* `teams` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id.
* `uid` - _required_

### Updates the specified webhook subscription.<br/>
> <br/>
> The following properties can be mutated:<br/>
> <br/>
> * `description`<br/>
> * `url`<br/>
> * `active`<br/>
> * `events`

*Tags:* `teams` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id
* `uid` - _required_

### All members of a team.<br/>
> <br/>
> Returns all members of the specified team. Any member of any of the<br/>
> team's groups is considered a member of the team. This includes users<br/>
> in groups that may not actually have access to any of the team's<br/>
> repositories.<br/>
> <br/>
> Note that members using the "private profile" feature are not included.

*Tags:* `teams`

#### Input Parameters
* `username` - _required_

### Find account level variables.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.

### Create an account level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.

### Delete a team level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `variable_uuid` - _required_ - The UUID of the variable to delete.

### Retrieve a team level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `variable_uuid` - _required_ - The UUID of the variable to retrieve.

### Update a team level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `variable_uuid` - _required_ - The UUID of the variable.

### All repositories owned by a user/team. This includes private<br/>
> repositories, but filtered down to the ones that the calling user has<br/>
> access to.

*Tags:* `users` `teams`

#### Input Parameters
* `username` - _required_

### Returns the currently logged in user.

*Tags:* `users`

### Returns all the authenticated user's email addresses. Both<br/>
> confirmed and unconfirmed.

*Tags:* `users`

### Returns details about a specific one of the authenticated user's<br/>
> email addresses.<br/>
> <br/>
> Details describe whether the address has been confirmed by the user and<br/>
> whether it is the user's primary address or not.

*Tags:* `users`

#### Input Parameters
* `email` - _required_

### Gets the public information associated with a user account.<br/>
> <br/>
> If the user's profile is private, `location`, `website` and<br/>
> `created_on` elements are omitted.

*Tags:* `users`

#### Input Parameters
* `username` - _required_ - The account's username or UUID.

### Returns the list of accounts that are following this team.

*Tags:* `users`

#### Input Parameters
* `username` - _required_ - The account's username

### Returns the list of accounts this user is following.

*Tags:* `users`

#### Input Parameters
* `username` - _required_ - The user's username

### Returns a paginated list of webhooks installed on this user account.

*Tags:* `users` `webhooks`

#### Input Parameters
* `username` - _required_

### Creates a new webhook on the specified user account.<br/>
> <br/>
> Account-level webhooks are fired for events from all repositories<br/>
> belonging to that account.<br/>
> <br/>
> Note that one can only register webhooks on one's own account, not that<br/>
> of others.

*Tags:* `users` `webhooks`

#### Input Parameters
* `username` - _required_

### Deletes the specified webhook subscription from the given user<br/>
> account.

*Tags:* `users` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id
* `uid` - _required_

### Returns the webhook with the specified id installed on the given<br/>
> user account.

*Tags:* `users` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id.
* `uid` - _required_

### Updates the specified webhook subscription.<br/>
> <br/>
> The following properties can be mutated:<br/>
> <br/>
> * `description`<br/>
> * `url`<br/>
> * `active`<br/>
> * `events`

*Tags:* `users` `webhooks`

#### Input Parameters
* `uid` - _required_ - The installed webhook's id
* `uid` - _required_

### Find user level variables.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.

### Create a user level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.

### Delete an account level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `variable_uuid` - _required_ - The UUID of the variable to delete.

### Retrieve a user level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `variable_uuid` - _required_ - The UUID of the variable to retrieve.

### Update a user level variable.

*Tags:* `pipelines`

#### Input Parameters
* `username` - _required_ - The account.
* `variable_uuid` - _required_ - The UUID of the variable.

### All repositories owned by a user/team. This includes private<br/>
> repositories, but filtered down to the ones that the calling user has<br/>
> access to.

*Tags:* `users` `teams`

#### Input Parameters
* `username` - _required_

## License

**flow**ground :- Telekom iPaaS / bitbucket-org-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
