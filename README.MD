# Webhooks with github

## Create github access token

Export token
```
export TOKEN="asdf-asdf-asdf-asdf"
``

## Create postbin

Go to https://postb.in/, create a bin. Export bin id:
```
export BIN_ID="1581493698910-3715858794748"
```

## Create webhook on repository

Edit webhook_create.json set url to postbin url.

Create webhook on repository
```
curl -u cretzel:$TOKEN -X POST -d @webhook_create.json https://api.github.com/repos/cretzel/github-webhooks-example/hooks

{
  "type": "Repository",
  "id": 182903153,
  "name": "web",
  "active": true,
  "events": [
    "pull_request",
    "push"
  ],
  "config": {
    "content_type": "json",
    "insecure_ssl": "0",
    "secret": "********",
    "url": "https://postb.in/1581493698910-3715858794748"
  },
  "updated_at": "2020-02-12T07:53:27Z",
  "created_at": "2020-02-12T07:53:27Z",
  "url": "https://api.github.com/repos/cretzel/github-webhooks-example/hooks/182903153",
  "test_url": "https://api.github.com/repos/cretzel/github-webhooks-example/hooks/182903153/test",
  "ping_url": "https://api.github.com/repos/cretzel/github-webhooks-example/hooks/182903153/pings",
  "last_response": {
    "code": null,
    "status": "unused",
    "message": null
  }
}
```

## Trigger push event
Commit to repository

## Get webhook calls from postbin

```
curl https://postb.in/api/bin/$BIN_ID/req/shift | jq

b-webhooks-example",
      "full_name": "cretzel/github-webhooks-example",
      "private": false,
      "owner": {
        "name": "cretzel",
        "email": "nick.wiedenbrueck@gmail.com",
        "login": "cretzel",
        "id": 142063,
        "node_id": "MDQ6VXNlcjE0MjA2Mw==",
        "avatar_url": "https://avatars1.githubusercontent.com/u/142063?v=4",
        "gravatar_id": "",
        "url": "https://api.github.com/users/cretzel",
        "html_url": "https://github.com/cretzel",
        "followers_url": "https://api.github.com/users/cretzel/followers",
        "following_url": "https://api.github.com/users/cretzel/following{/other_user}",
        "gists_url": "https://api.github.com/users/cretzel/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/cretzel/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/cretzel/subscriptions",
        "organizations_url": "https://api.github.com/users/cretzel/orgs",
        "repos_url": "https://api.github.com/users/cretzel/repos",
        "events_url": "https://api.github.com/users/cretzel/events{/privacy}",
        "received_events_url": "https://api.github.com/users/cretzel/received_events",
        "type": "User",
        "site_admin": false
      },
      "html_url": "https://github.com/cretzel/github-webhooks-example",
      "description": null,
      "fork": false,
      "url": "https://github.com/cretzel/github-webhooks-example",
      "forks_url": "https://api.github.com/repos/cretzel/github-webhooks-example/forks",
      "keys_url": "https://api.github.com/repos/cretzel/github-webhooks-example/keys{/key_id}",
      "collaborators_url": "https://api.github.com/repos/cretzel/github-webhooks-example/collaborators{/collaborator}",
      "teams_url": "https://api.github.com/repos/cretzel/github-webhooks-example/teams",
      "hooks_url": "https://api.github.com/repos/cretzel/github-webhooks-example/hooks",
      "issue_events_url": "https://api.github.com/repos/cretzel/github-webhooks-example/issues/events{/number}",
      "events_url": "https://api.github.com/repos/cretzel/github-webhooks-example/events",
      "assignees_url": "https://api.github.com/repos/cretzel/github-webhooks-example/assignees{/user}",
      "branches_url": "https://api.github.com/repos/cretzel/github-webhooks-example/branches{/branch}",
      "tags_url": "https://api.github.com/repos/cretzel/github-webhooks-example/tags",
      "blobs_url": "https://api.github.com/repos/cretzel/github-webhooks-example/git/blobs{/sha}",
      "git_tags_url": "https://api.github.com/repos/cretzel/github-webhooks-example/git/tags{/sha}",
      "git_refs_url": "https://api.github.com/repos/cretzel/github-webhooks-example/git/refs{/sha}",
      "trees_url": "https://api.github.com/repos/cretzel/github-webhooks-example/git/trees{/sha}",
      "statuses_url": "https://api.github.com/repos/cretzel/github-webhooks-example/statuses/{sha}",
      "languages_url": "https://api.github.com/repos/cretzel/github-webhooks-example/languages",
      "stargazers_url": "https://api.github.com/repos/cretzel/github-webhooks-example/stargazers",
      "contributors_url": "https://api.github.com/repos/cretzel/github-webhooks-example/contributors",
      "subscribers_url": "https://api.github.com/repos/cretzel/github-webhooks-example/subscribers",
      "subscription_url": "https://api.github.com/repos/cretzel/github-webhooks-example/subscription",
      "commits_url": "https://api.github.com/repos/cretzel/github-webhooks-example/commits{/sha}",
      "git_commits_url": "https://api.github.com/repos/cretzel/github-webhooks-example/git/commits{/sha}",
      "comments_url": "https://api.github.com/repos/cretzel/github-webhooks-example/comments{/number}",
      "issue_comment_url": "https://api.github.com/repos/cretzel/github-webhooks-example/issues/comments{/number}",
      "contents_url": "https://api.github.com/repos/cretzel/github-webhooks-example/contents/{+path}",
      "compare_url": "https://api.github.com/repos/cretzel/github-webhooks-example/compare/{base}...{head}",
      "merges_url": "https://api.github.com/repos/cretzel/github-webhooks-example/merges",
      "archive_url": "https://api.github.com/repos/cretzel/github-webhooks-example/{archive_format}{/ref}",
      "downloads_url": "https://api.github.com/repos/cretzel/github-webhooks-example/downloads",
      "issues_url": "https://api.github.com/repos/cretzel/github-webhooks-example/issues{/number}",
      "pulls_url": "https://api.github.com/repos/cretzel/github-webhooks-example/pulls{/number}",
      "milestones_url": "https://api.github.com/repos/cretzel/github-webhooks-example/milestones{/number}",
      "notifications_url": "https://api.github.com/repos/cretzel/github-webhooks-example/notifications{?since,all,participating}",
      "labels_url": "https://api.github.com/repos/cretzel/github-webhooks-example/labels{/name}",
      "releases_url": "https://api.github.com/repos/cretzel/github-webhooks-example/releases{/id}",
      "deployments_url": "https://api.github.com/repos/cretzel/github-webhooks-example/deployments",
      "created_at": 1581493490,
      "updated_at": "2020-02-12T07:44:50Z",
      "pushed_at": 1581494094,
      "git_url": "git://github.com/cretzel/github-webhooks-example.git",
      "ssh_url": "git@github.com:cretzel/github-webhooks-example.git",
      "clone_url": "https://github.com/cretzel/github-webhooks-example.git",
      "svn_url": "https://github.com/cretzel/github-webhooks-example",
      "homepage": null,
      "size": 0,
      "stargazers_count": 0,
      "watchers_count": 0,
      "language": null,
      "has_issues": true,
      "has_projects": true,
      "has_downloads": true,
      "has_wiki": true,
      "has_pages": false,
      "forks_count": 0,
      "mirror_url": null,
      "archived": false,
      "disabled": false,
      "open_issues_count": 0,
      "license": null,
      "forks": 0,
      "open_issues": 0,
      "watchers": 0,
      "default_branch": "master",
      "stargazers": 0,
      "master_branch": "master"
    },
    "pusher": {
      "name": "cretzel",
      "email": "nick.wiedenbrueck@gmail.com"
    },
    "sender": {
      "login": "cretzel",
      "id": 142063,
      "node_id": "MDQ6VXNlcjE0MjA2Mw==",
      "avatar_url": "https://avatars1.githubusercontent.com/u/142063?v=4",
      "gravatar_id": "",
      "url": "https://api.github.com/users/cretzel",
      "html_url": "https://github.com/cretzel",
      "followers_url": "https://api.github.com/users/cretzel/followers",
      "following_url": "https://api.github.com/users/cretzel/following{/other_user}",
      "gists_url": "https://api.github.com/users/cretzel/gists{/gist_id}",
      "starred_url": "https://api.github.com/users/cretzel/starred{/owner}{/repo}",
      "subscriptions_url": "https://api.github.com/users/cretzel/subscriptions",
      "organizations_url": "https://api.github.com/users/cretzel/orgs",
      "repos_url": "https://api.github.com/users/cretzel/repos",
      "events_url": "https://api.github.com/users/cretzel/events{/privacy}",
      "received_events_url": "https://api.github.com/users/cretzel/received_events",
      "type": "User",
      "site_admin": false
    },
    "created": true,
    "deleted": false,
    "forced": false,
    "base_ref": null,
    "compare": "https://github.com/cretzel/github-webhooks-example/commit/600bd9429d11",
    "commits": [
      {
        "id": "600bd9429d118b20a4f508a4006374e135c32537",
        "tree_id": "c5d5d7dee9a47cd08f5f4c2adce7a69aeef460a8",
        "distinct": true,
        "message": "initial commit",
        "timestamp": "2020-02-12T08:54:48+01:00",
        "url": "https://github.com/cretzel/github-webhooks-example/commit/600bd9429d118b20a4f508a4006374e135c32537",
        "author": {
          "name": "Nick Wiedenbrück",
          "email": "nick.wiedenbrueck@miele.com"
        },
        "committer": {
          "name": "Nick Wiedenbrück",
          "email": "nick.wiedenbrueck@miele.com"
        },
        "added": [
          "README.MD",
          "webhook_create.json"
        ],
        "removed": [],
        "modified": []
      }
    ],
    "head_commit": {
      "id": "600bd9429d118b20a4f508a4006374e135c32537",
      "tree_id": "c5d5d7dee9a47cd08f5f4c2adce7a69aeef460a8",
      "distinct": true,
      "message": "initial commit",
      "timestamp": "2020-02-12T08:54:48+01:00",
      "url": "https://github.com/cretzel/github-webhooks-example/commit/600bd9429d118b20a4f508a4006374e135c32537",
      "author": {
        "name": "Nick Wiedenbrück",
        "email": "nick.wiedenbrueck@miele.com"
      },
      "committer": {
        "name": "Nick Wiedenbrück",
        "email": "nick.wiedenbrueck@miele.com"
      },
      "added": [
        "README.MD",
        "webhook_create.json"
      ],
      "removed": [],
      "modified": []
    }
  },
  "ip": "140.82.115.244",
  "reqId": "1581494094875-2103422039654",
  "binId": "1581493698910-3715858794748",
  "inserted": 1581494094875
}
```

