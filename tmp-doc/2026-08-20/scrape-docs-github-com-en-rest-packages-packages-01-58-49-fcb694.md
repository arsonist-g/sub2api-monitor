---
url: https://docs.github.com/en/rest/packages/packages
fetched_at: 2026-08-19T17:58:49.518123+00:00
fetch_method: normal
---

[GitHub Docs](/en)

Search or ask Copilot

Select language: current language is English

Search or ask Copilot

Open menu

Collapse sidebarExpand sidebar

Scroll breadcrumbs leftScroll breadcrumbs right

The REST API is now versioned. For more information, see "[About API versioning](/rest/overview/api-versions)."

# REST API endpoints for packages

Use the REST API to interact with GitHub Packages.

## [About GitHub Packages](#about-github-packages)

GitHub Packages supports a range of package managers for publishing packages. For more information, see [Introduction to GitHub Packages](/en/packages/learn-github-packages/introduction-to-github-packages#supported-clients-and-formats).

After you publish a package, you can use the REST API to manage the package in your GitHub repositories and organizations. For more information, see [Deleting and restoring a package](/en/packages/learn-github-packages/deleting-and-restoring-a-package).

To use the REST API to manage GitHub Packages, you must authenticate using a personal access token (classic).

* To access package metadata, your token must include the `read:packages` scope.
* To delete packages and package versions, your token must include the `read:packages` and `delete:packages` scopes.
* To restore packages and package versions, your token must include the `read:packages` and `write:packages` scopes.

If your package is in a registry that supports granular permissions, then your token does not need the `repo` scope to access or manage this package. If your package is in a registry that only supports repository-scoped permissions, then your token must also include the `repo` scope since your package inherits permissions from a GitHub repository. For a list of registries that only support repository-scoped permissions, see [About permissions for GitHub Packages](/en/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages).

## [Get list of conflicting packages during Docker migration for organization](#get-list-of-conflicting-packages-during-docker-migration-for-organization)

Lists all packages that are in a specific organization, are readable by the requesting user, and that encountered a conflict during a Docker migration.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint.

### [Fine-grained access tokens for "Get list of conflicting packages during Docker migration for organization"](#get-list-of-conflicting-packages-during-docker-migration-for-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)
* [Fine-grained personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token)

The fine-grained token does not require any permissions.

This endpoint can be used without authentication if only public resources are requested.

### [Parameters for "Get list of conflicting packages during Docker migration for organization"](#get-list-of-conflicting-packages-during-docker-migration-for-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `org` string Required  The organization name. The name is not case sensitive. |

### [HTTP response status codes for "Get list of conflicting packages during Docker migration for organization"](#get-list-of-conflicting-packages-during-docker-migration-for-organization--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `401` | Requires authentication |
| `403` | Forbidden |

### [Code samples for "Get list of conflicting packages during Docker migration for organization"](#get-list-of-conflicting-packages-during-docker-migration-for-organization--code-samples)

#### Request example

get/orgs/{org}/docker/conflicts

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/docker/conflicts`

Response

`Status: 200`

`[ { "id": 197, "name": "hello_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/github", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "Organization", "site_admin": false }, "version_count": 1, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/hello_docker" }, { "id": 198, "name": "goodbye_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/github", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "Organization", "site_admin": false }, "version_count": 2, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/goodbye_docker", "created_at": "2020-05-20T22:19:11Z", "updated_at": "2020-05-20T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/goodbye_docker" } ]`

## [List packages for an organization](#list-packages-for-an-organization)

Lists packages in an organization readable by the user.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "List packages for an organization"](#list-packages-for-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "List packages for an organization"](#list-packages-for-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `org` string Required  The organization name. The name is not case sensitive. |

Query parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `visibility` string  The selected visibility of the packages. This parameter is optional and only filters an existing result set.  The `internal` visibility is only supported for GitHub Packages registries that allow for granular permissions. For other ecosystems `internal` is synonymous with `private`. For the list of GitHub Packages registries that support granular permissions, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."  Can be one of: `public`, `private`, `internal` |
| `page` integer  The page number of the results to fetch. For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `1` |
| `per_page` integer  The number of results per page (max 100). For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `30` |

### [HTTP response status codes for "List packages for an organization"](#list-packages-for-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `400` | The value of `per_page` multiplied by `page` cannot be greater than 10000. |
| `401` | Requires authentication |
| `403` | Forbidden |

### [Code samples for "List packages for an organization"](#list-packages-for-an-organization--code-samples)

#### Request example

get/orgs/{org}/packages

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ "https://api.github.com/orgs/ORG/packages?package_type=container"`

Response

`Status: 200`

`[ { "id": 197, "name": "hello_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/github", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "Organization", "site_admin": false }, "version_count": 1, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/hello_docker" }, { "id": 198, "name": "goodbye_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/github", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "Organization", "site_admin": false }, "version_count": 2, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/goodbye_docker", "created_at": "2020-05-20T22:19:11Z", "updated_at": "2020-05-20T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/goodbye_docker" } ]`

## [Get a package for an organization](#get-a-package-for-an-organization)

Gets a specific package in an organization.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Get a package for an organization"](#get-a-package-for-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Get a package for an organization"](#get-a-package-for-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `org` string Required  The organization name. The name is not case sensitive. |

### [HTTP response status codes for "Get a package for an organization"](#get-a-package-for-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |

### [Code samples for "Get a package for an organization"](#get-a-package-for-an-organization--code-samples)

#### Request example

get/orgs/{org}/packages/{package\_type}/{package\_name}

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME`

Response

`Status: 200`

`{ "id": 197, "name": "hello_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/github", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "Organization", "site_admin": false }, "version_count": 1, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/hello_docker" }`

## [Delete a package for an organization](#delete-a-package-for-an-organization)

Deletes an entire package in an organization. You cannot delete a public package if any version of the package has more than 5,000 downloads. In this scenario, contact GitHub support for further assistance.

The authenticated user must have admin permissions in the organization to use this endpoint. If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must also have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `delete:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Delete a package for an organization"](#delete-a-package-for-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Delete a package for an organization"](#delete-a-package-for-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `org` string Required  The organization name. The name is not case sensitive. |

### [HTTP response status codes for "Delete a package for an organization"](#delete-a-package-for-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Delete a package for an organization"](#delete-a-package-for-an-organization--code-samples)

#### Request example

delete/orgs/{org}/packages/{package\_type}/{package\_name}

Copy to clipboard curl request example

`curl -L \ -X DELETE \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME`

Response

`Status: 204`

## [Restore a package for an organization](#restore-a-package-for-an-organization)

Restores an entire package in an organization.

You can restore a deleted package under the following conditions:

* The package was deleted within the last 30 days.
* The same package namespace and version is still available and not reused for a new package. If the same package namespace is not available, you will not be able to restore your package. In this scenario, to restore the deleted package, you must delete the new package that uses the deleted package's namespace first.

The authenticated user must have admin permissions in the organization to use this endpoint. If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must also have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `write:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Restore a package for an organization"](#restore-a-package-for-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Restore a package for an organization"](#restore-a-package-for-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `org` string Required  The organization name. The name is not case sensitive. |

Query parameters

| Name, Type, Description |
| `token` string  package token |

### [HTTP response status codes for "Restore a package for an organization"](#restore-a-package-for-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Restore a package for an organization"](#restore-a-package-for-an-organization--code-samples)

#### Request example

post/orgs/{org}/packages/{package\_type}/{package\_name}/restore

Copy to clipboard curl request example

`curl -L \ -X POST \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/restore`

Response

`Status: 204`

## [List package versions for a package owned by an organization](#list-package-versions-for-a-package-owned-by-an-organization)

Lists package versions for a package owned by an organization.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "List package versions for a package owned by an organization"](#list-package-versions-for-a-package-owned-by-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "List package versions for a package owned by an organization"](#list-package-versions-for-a-package-owned-by-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `org` string Required  The organization name. The name is not case sensitive. |

Query parameters

| Name, Type, Description |
| `page` integer  The page number of the results to fetch. For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `1` |
| `per_page` integer  The number of results per page (max 100). For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `30` |
| `state` string  The state of the package, either active or deleted.  Default: `active`  Can be one of: `active`, `deleted` |

### [HTTP response status codes for "List package versions for a package owned by an organization"](#list-package-versions-for-a-package-owned-by-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "List package versions for a package owned by an organization"](#list-package-versions-for-a-package-owned-by-an-organization--code-samples)

#### Request example

get/orgs/{org}/packages/{package\_type}/{package\_name}/versions

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions`

Response

`Status: 200`

`[ { "id": 245301, "name": "1.0.4", "url": "https://api.github.com/orgs/octo-org/packages/npm/hello-world-npm/versions/245301", "package_html_url": "https://github.com/octo-org/hello-world-npm/packages/43752", "created_at": "2019-11-05T22:49:04Z", "updated_at": "2019-11-05T22:49:04Z", "html_url": "https://github.com/octo-org/hello-world-npm/packages/43752?version=1.0.4", "metadata": { "package_type": "npm" } }, { "id": 209672, "name": "1.0.3", "url": "https://api.github.com/orgs/octo-org/packages/npm/hello-world-npm/versions/209672", "package_html_url": "https://github.com/octo-org/hello-world-npm/packages/43752", "created_at": "2019-10-29T15:42:11Z", "updated_at": "2019-10-29T15:42:12Z", "html_url": "https://github.com/octo-org/hello-world-npm/packages/43752?version=1.0.3", "metadata": { "package_type": "npm" } } ]`

## [Get a package version for an organization](#get-a-package-version-for-an-organization)

Gets a specific package version in an organization.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Get a package version for an organization"](#get-a-package-version-for-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Get a package version for an organization"](#get-a-package-version-for-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `org` string Required  The organization name. The name is not case sensitive. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Get a package version for an organization"](#get-a-package-version-for-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |

### [Code samples for "Get a package version for an organization"](#get-a-package-version-for-an-organization--code-samples)

#### Request example

get/orgs/{org}/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID`

Response

`Status: 200`

`{ "id": 836, "name": "sha256:b3d3e366b55f9a54599220198b3db5da8f53592acbbb7dc7e4e9878762fc5344", "url": "https://api.github.com/orgs/github/packages/container/hello_docker/versions/836", "package_html_url": "https://github.com/orgs/github/packages/container/package/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/hello_docker/836", "metadata": { "package_type": "container", "container": { "tags": [ "latest" ] } } }`

## [Delete package version for an organization](#delete-package-version-for-an-organization)

Deletes a specific package version in an organization. If the package is public and the package version has more than 5,000 downloads, you cannot delete the package version. In this scenario, contact GitHub support for further assistance.

The authenticated user must have admin permissions in the organization to use this endpoint. If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must also have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `delete:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Delete package version for an organization"](#delete-package-version-for-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Delete package version for an organization"](#delete-package-version-for-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `org` string Required  The organization name. The name is not case sensitive. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Delete package version for an organization"](#delete-package-version-for-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Delete package version for an organization"](#delete-package-version-for-an-organization--code-samples)

#### Request example

delete/orgs/{org}/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}

Copy to clipboard curl request example

`curl -L \ -X DELETE \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID`

Response

`Status: 204`

## [Restore package version for an organization](#restore-package-version-for-an-organization)

Restores a specific package version in an organization.

You can restore a deleted package under the following conditions:

* The package was deleted within the last 30 days.
* The same package namespace and version is still available and not reused for a new package. If the same package namespace is not available, you will not be able to restore your package. In this scenario, to restore the deleted package, you must delete the new package that uses the deleted package's namespace first.

The authenticated user must have admin permissions in the organization to use this endpoint. If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must also have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `write:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Restore package version for an organization"](#restore-package-version-for-an-organization--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Restore package version for an organization"](#restore-package-version-for-an-organization--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `org` string Required  The organization name. The name is not case sensitive. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Restore package version for an organization"](#restore-package-version-for-an-organization--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Restore package version for an organization"](#restore-package-version-for-an-organization--code-samples)

#### Request example

post/orgs/{org}/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}/restore

Copy to clipboard curl request example

`curl -L \ -X POST \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID/restore`

Response

`Status: 204`

## [Get list of conflicting packages during Docker migration for authenticated-user](#get-list-of-conflicting-packages-during-docker-migration-for-authenticated-user)

Lists all packages that are owned by the authenticated user within the user's namespace, and that encountered a conflict during a Docker migration.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint.

### [Fine-grained access tokens for "Get list of conflicting packages during Docker migration for authenticated-user"](#get-list-of-conflicting-packages-during-docker-migration-for-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [Fine-grained personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token)

The fine-grained token does not require any permissions.

### [HTTP response status codes for "Get list of conflicting packages during Docker migration for authenticated-user"](#get-list-of-conflicting-packages-during-docker-migration-for-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |

### [Code samples for "Get list of conflicting packages during Docker migration for authenticated-user"](#get-list-of-conflicting-packages-during-docker-migration-for-authenticated-user--code-samples)

#### Request example

get/user/docker/conflicts

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/docker/conflicts`

Response

`Status: 200`

`[ { "id": 197, "name": "hello_docker", "package_type": "container", "owner": { "login": "octocat", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.octocatusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 1, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/hello_docker" }, { "id": 198, "name": "goodbye_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 2, "visibility": "private", "url": "https://api.github.com/user/octocat/packages/container/goodbye_docker", "created_at": "2020-05-20T22:19:11Z", "updated_at": "2020-05-20T22:19:11Z", "html_url": "https://github.com/user/octocat/packages/container/package/goodbye_docker" } ]`

## [List packages for the authenticated user's namespace](#list-packages-for-the-authenticated-users-namespace)

Lists packages owned by the authenticated user within the user's namespace.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "List packages for the authenticated user's namespace"](#list-packages-for-the-authenticated-users-namespace--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "List packages for the authenticated user's namespace"](#list-packages-for-the-authenticated-users-namespace--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Query parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `visibility` string  The selected visibility of the packages. This parameter is optional and only filters an existing result set.  The `internal` visibility is only supported for GitHub Packages registries that allow for granular permissions. For other ecosystems `internal` is synonymous with `private`. For the list of GitHub Packages registries that support granular permissions, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."  Can be one of: `public`, `private`, `internal` |
| `page` integer  The page number of the results to fetch. For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `1` |
| `per_page` integer  The number of results per page (max 100). For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `30` |

### [HTTP response status codes for "List packages for the authenticated user's namespace"](#list-packages-for-the-authenticated-users-namespace--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `400` | The value of `per_page` multiplied by `page` cannot be greater than 10000. |

### [Code samples for "List packages for the authenticated user's namespace"](#list-packages-for-the-authenticated-users-namespace--code-samples)

#### Request example

get/user/packages

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ "https://api.github.com/user/packages?package_type=container"`

Response

`Status: 200`

`[ { "id": 197, "name": "hello_docker", "package_type": "container", "owner": { "login": "octocat", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.octocatusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 1, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/hello_docker" }, { "id": 198, "name": "goodbye_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 2, "visibility": "private", "url": "https://api.github.com/user/octocat/packages/container/goodbye_docker", "created_at": "2020-05-20T22:19:11Z", "updated_at": "2020-05-20T22:19:11Z", "html_url": "https://github.com/user/octocat/packages/container/package/goodbye_docker" } ]`

## [Get a package for the authenticated user](#get-a-package-for-the-authenticated-user)

Gets a specific package for a package owned by the authenticated user.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Get a package for the authenticated user"](#get-a-package-for-the-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Get a package for the authenticated user"](#get-a-package-for-the-authenticated-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |

### [HTTP response status codes for "Get a package for the authenticated user"](#get-a-package-for-the-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |

### [Code samples for "Get a package for the authenticated user"](#get-a-package-for-the-authenticated-user--code-samples)

#### Request example

get/user/packages/{package\_type}/{package\_name}

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/packages/PACKAGE_TYPE/PACKAGE_NAME`

Response

`Status: 200`

`{ "id": 40201, "name": "octo-name", "package_type": "rubygems", "owner": { "login": "octocat", "id": 209477, "node_id": "MDQ6VXNlcjIwOTQ3Nw==", "avatar_url": "https://avatars.githubusercontent.com/u/209477?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/octocat", "followers_url": "https://api.github.com/users/octocat/followers", "following_url": "https://api.github.com/users/octocat/following{/other_user}", "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}", "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/octocat/subscriptions", "organizations_url": "https://api.github.com/users/octocat/orgs", "repos_url": "https://api.github.com/users/octocat/repos", "events_url": "https://api.github.com/users/octocat/events{/privacy}", "received_events_url": "https://api.github.com/users/octocat/received_events", "type": "User", "site_admin": true }, "version_count": 3, "visibility": "public", "url": "https://api.github.com/users/octocat/packages/rubygems/octo-name", "created_at": "2019-10-20T14:17:14Z", "updated_at": "2019-10-20T14:17:14Z", "repository": { "id": 216219492, "node_id": "MDEwOlJlcG9zaXRvcnkyMTYyMTk0OTI=", "name": "octo-name-repo", "full_name": "octocat/octo-name-repo", "private": false, "owner": { "login": "octocat", "id": 209477, "node_id": "MDQ6VXNlcjIwOTQ3Nw==", "avatar_url": "https://avatars.githubusercontent.com/u/209477?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/octocat", "followers_url": "https://api.github.com/users/octocat/followers", "following_url": "https://api.github.com/users/octocat/following{/other_user}", "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}", "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/octocat/subscriptions", "organizations_url": "https://api.github.com/users/octocat/orgs", "repos_url": "https://api.github.com/users/octocat/repos", "events_url": "https://api.github.com/users/octocat/events{/privacy}", "received_events_url": "https://api.github.com/users/octocat/received_events", "type": "User", "site_admin": true }, "html_url": "https://github.com/octocat/octo-name-repo", "description": "Project for octocats", "fork": false, "url": "https://api.github.com/repos/octocat/octo-name-repo", "forks_url": "https://api.github.com/repos/octocat/octo-name-repo/forks", "keys_url": "https://api.github.com/repos/octocat/octo-name-repo/keys{/key_id}", "collaborators_url": "https://api.github.com/repos/octocat/octo-name-repo/collaborators{/collaborator}", "teams_url": "https://api.github.com/repos/octocat/octo-name-repo/teams", "hooks_url": "https://api.github.com/repos/octocat/octo-name-repo/hooks", "issue_events_url": "https://api.github.com/repos/octocat/octo-name-repo/issues/events{/number}", "events_url": "https://api.github.com/repos/octocat/octo-name-repo/events", "assignees_url": "https://api.github.com/repos/octocat/octo-name-repo/assignees{/user}", "branches_url": "https://api.github.com/repos/octocat/octo-name-repo/branches{/branch}", "tags_url": "https://api.github.com/repos/octocat/octo-name-repo/tags", "blobs_url": "https://api.github.com/repos/octocat/octo-name-repo/git/blobs{/sha}", "git_tags_url": "https://api.github.com/repos/octocat/octo-name-repo/git/tags{/sha}", "git_refs_url": "https://api.github.com/repos/octocat/octo-name-repo/git/refs{/sha}", "trees_url": "https://api.github.com/repos/octocat/octo-name-repo/git/trees{/sha}", "statuses_url": "https://api.github.com/repos/octocat/octo-name-repo/statuses/{sha}", "languages_url": "https://api.github.com/repos/octocat/octo-name-repo/languages", "stargazers_url": "https://api.github.com/repos/octocat/octo-name-repo/stargazers", "contributors_url": "https://api.github.com/repos/octocat/octo-name-repo/contributors", "subscribers_url": "https://api.github.com/repos/octocat/octo-name-repo/subscribers", "subscription_url": "https://api.github.com/repos/octocat/octo-name-repo/subscription", "commits_url": "https://api.github.com/repos/octocat/octo-name-repo/commits{/sha}", "git_commits_url": "https://api.github.com/repos/octocat/octo-name-repo/git/commits{/sha}", "comments_url": "https://api.github.com/repos/octocat/octo-name-repo/comments{/number}", "issue_comment_url": "https://api.github.com/repos/octocat/octo-name-repo/issues/comments{/number}", "contents_url": "https://api.github.com/repos/octocat/octo-name-repo/contents/{+path}", "compare_url": "https://api.github.com/repos/octocat/octo-name-repo/compare/{base}...{head}", "merges_url": "https://api.github.com/repos/octocat/octo-name-repo/merges", "archive_url": "https://api.github.com/repos/octocat/octo-name-repo/{archive_format}{/ref}", "downloads_url": "https://api.github.com/repos/octocat/octo-name-repo/downloads", "issues_url": "https://api.github.com/repos/octocat/octo-name-repo/issues{/number}", "pulls_url": "https://api.github.com/repos/octocat/octo-name-repo/pulls{/number}", "milestones_url": "https://api.github.com/repos/octocat/octo-name-repo/milestones{/number}", "notifications_url": "https://api.github.com/repos/octocat/octo-name-repo/notifications{?since,all,participating}", "labels_url": "https://api.github.com/repos/octocat/octo-name-repo/labels{/name}", "releases_url": "https://api.github.com/repos/octocat/octo-name-repo/releases{/id}", "deployments_url": "https://api.github.com/repos/octocat/octo-name-repo/deployments" }, "html_url": "https://github.com/octocat/octo-name-repo/packages/40201" }`

## [Delete a package for the authenticated user](#delete-a-package-for-the-authenticated-user)

Deletes a package owned by the authenticated user. You cannot delete a public package if any version of the package has more than 5,000 downloads. In this scenario, contact GitHub support for further assistance.

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `delete:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Delete a package for the authenticated user"](#delete-a-package-for-the-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Delete a package for the authenticated user"](#delete-a-package-for-the-authenticated-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |

### [HTTP response status codes for "Delete a package for the authenticated user"](#delete-a-package-for-the-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Delete a package for the authenticated user"](#delete-a-package-for-the-authenticated-user--code-samples)

#### Request example

delete/user/packages/{package\_type}/{package\_name}

Copy to clipboard curl request example

`curl -L \ -X DELETE \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/packages/PACKAGE_TYPE/PACKAGE_NAME`

Response

`Status: 204`

## [Restore a package for the authenticated user](#restore-a-package-for-the-authenticated-user)

Restores a package owned by the authenticated user.

You can restore a deleted package under the following conditions:

* The package was deleted within the last 30 days.
* The same package namespace and version is still available and not reused for a new package. If the same package namespace is not available, you will not be able to restore your package. In this scenario, to restore the deleted package, you must delete the new package that uses the deleted package's namespace first.

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `write:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Restore a package for the authenticated user"](#restore-a-package-for-the-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Restore a package for the authenticated user"](#restore-a-package-for-the-authenticated-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |

Query parameters

| Name, Type, Description |
| `token` string  package token |

### [HTTP response status codes for "Restore a package for the authenticated user"](#restore-a-package-for-the-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Restore a package for the authenticated user"](#restore-a-package-for-the-authenticated-user--code-samples)

#### Request example

post/user/packages/{package\_type}/{package\_name}/restore

Copy to clipboard curl request example

`curl -L \ -X POST \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/packages/PACKAGE_TYPE/PACKAGE_NAME/restore`

Response

`Status: 204`

## [List package versions for a package owned by the authenticated user](#list-package-versions-for-a-package-owned-by-the-authenticated-user)

Lists package versions for a package owned by the authenticated user.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "List package versions for a package owned by the authenticated user"](#list-package-versions-for-a-package-owned-by-the-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "List package versions for a package owned by the authenticated user"](#list-package-versions-for-a-package-owned-by-the-authenticated-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |

Query parameters

| Name, Type, Description |
| `page` integer  The page number of the results to fetch. For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `1` |
| `per_page` integer  The number of results per page (max 100). For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `30` |
| `state` string  The state of the package, either active or deleted.  Default: `active`  Can be one of: `active`, `deleted` |

### [HTTP response status codes for "List package versions for a package owned by the authenticated user"](#list-package-versions-for-a-package-owned-by-the-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "List package versions for a package owned by the authenticated user"](#list-package-versions-for-a-package-owned-by-the-authenticated-user--code-samples)

#### Request example

get/user/packages/{package\_type}/{package\_name}/versions

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/packages/PACKAGE_TYPE/PACKAGE_NAME/versions`

Response

`Status: 200`

`[ { "id": 45763, "name": "sha256:08a44bab0bddaddd8837a8b381aebc2e4b933768b981685a9e088360af0d3dd9", "url": "https://api.github.com/users/octocat/packages/container/hello_docker/versions/45763", "package_html_url": "https://github.com/users/octocat/packages/container/package/hello_docker", "created_at": "2020-09-11T21:56:40Z", "updated_at": "2021-02-05T21:32:32Z", "html_url": "https://github.com/users/octocat/packages/container/hello_docker/45763", "metadata": { "package_type": "container", "container": { "tags": [ "latest" ] } } }, { "id": 881, "name": "sha256:b3d3e366b55f9a54599220198b3db5da8f53592acbbb7dc7e4e9878762fc5344", "url": "https://api.github.com/users/octocat/packages/container/hello_docker/versions/881", "package_html_url": "https://github.com/users/octocat/packages/container/package/hello_docker", "created_at": "2020-05-21T22:22:20Z", "updated_at": "2021-02-05T21:32:32Z", "html_url": "https://github.com/users/octocat/packages/container/hello_docker/881", "metadata": { "package_type": "container", "container": { "tags": [] } } } ]`

## [Get a package version for the authenticated user](#get-a-package-version-for-the-authenticated-user)

Gets a specific package version for a package owned by the authenticated user.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Get a package version for the authenticated user"](#get-a-package-version-for-the-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Get a package version for the authenticated user"](#get-a-package-version-for-the-authenticated-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Get a package version for the authenticated user"](#get-a-package-version-for-the-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |

### [Code samples for "Get a package version for the authenticated user"](#get-a-package-version-for-the-authenticated-user--code-samples)

#### Request example

get/user/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID`

Response

`Status: 200`

`{ "id": 214, "name": "sha256:3561f0cff06caccddb99c93bd26e712fcc56a811de0f8ea7a17bb865f30b176a", "url": "https://api.github.com/users/octocat/packages/container/hello_docker/versions/214", "package_html_url": "https://github.com/users/octocat/packages/container/package/hello_docker", "created_at": "2020-05-15T03:46:45Z", "updated_at": "2020-05-15T03:46:45Z", "html_url": "https://github.com/users/octocat/packages/container/hello_docker/214", "metadata": { "package_type": "container", "container": { "tags": [ "1.13.6" ] } } }`

## [Delete a package version for the authenticated user](#delete-a-package-version-for-the-authenticated-user)

Deletes a specific package version for a package owned by the authenticated user. If the package is public and the package version has more than 5,000 downloads, you cannot delete the package version. In this scenario, contact GitHub support for further assistance.

The authenticated user must have admin permissions in the organization to use this endpoint.

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `delete:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Delete a package version for the authenticated user"](#delete-a-package-version-for-the-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Delete a package version for the authenticated user"](#delete-a-package-version-for-the-authenticated-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Delete a package version for the authenticated user"](#delete-a-package-version-for-the-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Delete a package version for the authenticated user"](#delete-a-package-version-for-the-authenticated-user--code-samples)

#### Request example

delete/user/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}

Copy to clipboard curl request example

`curl -L \ -X DELETE \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID`

Response

`Status: 204`

## [Restore a package version for the authenticated user](#restore-a-package-version-for-the-authenticated-user)

Restores a package version owned by the authenticated user.

You can restore a deleted package version under the following conditions:

* The package was deleted within the last 30 days.
* The same package namespace and version is still available and not reused for a new package. If the same package namespace is not available, you will not be able to restore your package. In this scenario, to restore the deleted package, you must delete the new package that uses the deleted package's namespace first.

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `write:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Restore a package version for the authenticated user"](#restore-a-package-version-for-the-authenticated-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Restore a package version for the authenticated user"](#restore-a-package-version-for-the-authenticated-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Restore a package version for the authenticated user"](#restore-a-package-version-for-the-authenticated-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Restore a package version for the authenticated user"](#restore-a-package-version-for-the-authenticated-user--code-samples)

#### Request example

post/user/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}/restore

Copy to clipboard curl request example

`curl -L \ -X POST \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/user/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID/restore`

Response

`Status: 204`

## [Get list of conflicting packages during Docker migration for user](#get-list-of-conflicting-packages-during-docker-migration-for-user)

Lists all packages that are in a specific user's namespace, that the requesting user has access to, and that encountered a conflict during Docker migration.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint.

### [Fine-grained access tokens for "Get list of conflicting packages during Docker migration for user"](#get-list-of-conflicting-packages-during-docker-migration-for-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)
* [Fine-grained personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token)

The fine-grained token does not require any permissions.

This endpoint can be used without authentication if only public resources are requested.

### [Parameters for "Get list of conflicting packages during Docker migration for user"](#get-list-of-conflicting-packages-during-docker-migration-for-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `username` string Required  The handle for the GitHub user account. |

### [HTTP response status codes for "Get list of conflicting packages during Docker migration for user"](#get-list-of-conflicting-packages-during-docker-migration-for-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `401` | Requires authentication |
| `403` | Forbidden |

### [Code samples for "Get list of conflicting packages during Docker migration for user"](#get-list-of-conflicting-packages-during-docker-migration-for-user--code-samples)

#### Request example

get/users/{username}/docker/conflicts

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/docker/conflicts`

Response

`Status: 200`

`[ { "id": 197, "name": "hello_docker", "package_type": "container", "owner": { "login": "octocat", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.octocatusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 1, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/hello_docker" }, { "id": 198, "name": "goodbye_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 2, "visibility": "private", "url": "https://api.github.com/user/octocat/packages/container/goodbye_docker", "created_at": "2020-05-20T22:19:11Z", "updated_at": "2020-05-20T22:19:11Z", "html_url": "https://github.com/user/octocat/packages/container/package/goodbye_docker" } ]`

## [List packages for a user](#list-packages-for-a-user)

Lists all packages in a user's namespace for which the requesting user has access.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "List packages for a user"](#list-packages-for-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "List packages for a user"](#list-packages-for-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `username` string Required  The handle for the GitHub user account. |

Query parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `visibility` string  The selected visibility of the packages. This parameter is optional and only filters an existing result set.  The `internal` visibility is only supported for GitHub Packages registries that allow for granular permissions. For other ecosystems `internal` is synonymous with `private`. For the list of GitHub Packages registries that support granular permissions, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."  Can be one of: `public`, `private`, `internal` |
| `page` integer  The page number of the results to fetch. For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `1` |
| `per_page` integer  The number of results per page (max 100). For more information, see "[Using pagination in the REST API](https://docs.github.com/rest/using-the-rest-api/using-pagination-in-the-rest-api)."  Default: `30` |

### [HTTP response status codes for "List packages for a user"](#list-packages-for-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `400` | The value of `per_page` multiplied by `page` cannot be greater than 10000. |
| `401` | Requires authentication |
| `403` | Forbidden |

### [Code samples for "List packages for a user"](#list-packages-for-a-user--code-samples)

#### Request example

get/users/{username}/packages

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ "https://api.github.com/users/USERNAME/packages?package_type=container"`

Response

`Status: 200`

`[ { "id": 197, "name": "hello_docker", "package_type": "container", "owner": { "login": "octocat", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.octocatusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 1, "visibility": "private", "url": "https://api.github.com/orgs/github/packages/container/hello_docker", "created_at": "2020-05-19T22:19:11Z", "updated_at": "2020-05-19T22:19:11Z", "html_url": "https://github.com/orgs/github/packages/container/package/hello_docker" }, { "id": 198, "name": "goodbye_docker", "package_type": "container", "owner": { "login": "github", "id": 9919, "node_id": "MDEyOk9yZ2FuaXphdGlvbjk5MTk=", "avatar_url": "https://avatars.githubusercontent.com/u/9919?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/github", "followers_url": "https://api.github.com/users/github/followers", "following_url": "https://api.github.com/users/github/following{/other_user}", "gists_url": "https://api.github.com/users/github/gists{/gist_id}", "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/github/subscriptions", "organizations_url": "https://api.github.com/users/github/orgs", "repos_url": "https://api.github.com/users/github/repos", "events_url": "https://api.github.com/users/github/events{/privacy}", "received_events_url": "https://api.github.com/users/github/received_events", "type": "User", "site_admin": false }, "version_count": 2, "visibility": "private", "url": "https://api.github.com/user/octocat/packages/container/goodbye_docker", "created_at": "2020-05-20T22:19:11Z", "updated_at": "2020-05-20T22:19:11Z", "html_url": "https://github.com/user/octocat/packages/container/package/goodbye_docker" } ]`

## [Get a package for a user](#get-a-package-for-a-user)

Gets a specific package metadata for a public package owned by a user.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Get a package for a user"](#get-a-package-for-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Get a package for a user"](#get-a-package-for-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `username` string Required  The handle for the GitHub user account. |

### [HTTP response status codes for "Get a package for a user"](#get-a-package-for-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |

### [Code samples for "Get a package for a user"](#get-a-package-for-a-user--code-samples)

#### Request example

get/users/{username}/packages/{package\_type}/{package\_name}

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/packages/PACKAGE_TYPE/PACKAGE_NAME`

Response

`Status: 200`

`{ "id": 40201, "name": "octo-name", "package_type": "rubygems", "owner": { "login": "octocat", "id": 209477, "node_id": "MDQ6VXNlcjIwOTQ3Nw==", "avatar_url": "https://avatars.githubusercontent.com/u/209477?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/octocat", "followers_url": "https://api.github.com/users/octocat/followers", "following_url": "https://api.github.com/users/octocat/following{/other_user}", "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}", "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/octocat/subscriptions", "organizations_url": "https://api.github.com/users/octocat/orgs", "repos_url": "https://api.github.com/users/octocat/repos", "events_url": "https://api.github.com/users/octocat/events{/privacy}", "received_events_url": "https://api.github.com/users/octocat/received_events", "type": "User", "site_admin": true }, "version_count": 3, "visibility": "public", "url": "https://api.github.com/users/octocat/packages/rubygems/octo-name", "created_at": "2019-10-20T14:17:14Z", "updated_at": "2019-10-20T14:17:14Z", "repository": { "id": 216219492, "node_id": "MDEwOlJlcG9zaXRvcnkyMTYyMTk0OTI=", "name": "octo-name-repo", "full_name": "octocat/octo-name-repo", "private": false, "owner": { "login": "octocat", "id": 209477, "node_id": "MDQ6VXNlcjIwOTQ3Nw==", "avatar_url": "https://avatars.githubusercontent.com/u/209477?v=4", "gravatar_id": "", "url": "https://api.github.com/users/octocat", "html_url": "https://github.com/octocat", "followers_url": "https://api.github.com/users/octocat/followers", "following_url": "https://api.github.com/users/octocat/following{/other_user}", "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}", "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}", "subscriptions_url": "https://api.github.com/users/octocat/subscriptions", "organizations_url": "https://api.github.com/users/octocat/orgs", "repos_url": "https://api.github.com/users/octocat/repos", "events_url": "https://api.github.com/users/octocat/events{/privacy}", "received_events_url": "https://api.github.com/users/octocat/received_events", "type": "User", "site_admin": true }, "html_url": "https://github.com/octocat/octo-name-repo", "description": "Project for octocats", "fork": false, "url": "https://api.github.com/repos/octocat/octo-name-repo", "forks_url": "https://api.github.com/repos/octocat/octo-name-repo/forks", "keys_url": "https://api.github.com/repos/octocat/octo-name-repo/keys{/key_id}", "collaborators_url": "https://api.github.com/repos/octocat/octo-name-repo/collaborators{/collaborator}", "teams_url": "https://api.github.com/repos/octocat/octo-name-repo/teams", "hooks_url": "https://api.github.com/repos/octocat/octo-name-repo/hooks", "issue_events_url": "https://api.github.com/repos/octocat/octo-name-repo/issues/events{/number}", "events_url": "https://api.github.com/repos/octocat/octo-name-repo/events", "assignees_url": "https://api.github.com/repos/octocat/octo-name-repo/assignees{/user}", "branches_url": "https://api.github.com/repos/octocat/octo-name-repo/branches{/branch}", "tags_url": "https://api.github.com/repos/octocat/octo-name-repo/tags", "blobs_url": "https://api.github.com/repos/octocat/octo-name-repo/git/blobs{/sha}", "git_tags_url": "https://api.github.com/repos/octocat/octo-name-repo/git/tags{/sha}", "git_refs_url": "https://api.github.com/repos/octocat/octo-name-repo/git/refs{/sha}", "trees_url": "https://api.github.com/repos/octocat/octo-name-repo/git/trees{/sha}", "statuses_url": "https://api.github.com/repos/octocat/octo-name-repo/statuses/{sha}", "languages_url": "https://api.github.com/repos/octocat/octo-name-repo/languages", "stargazers_url": "https://api.github.com/repos/octocat/octo-name-repo/stargazers", "contributors_url": "https://api.github.com/repos/octocat/octo-name-repo/contributors", "subscribers_url": "https://api.github.com/repos/octocat/octo-name-repo/subscribers", "subscription_url": "https://api.github.com/repos/octocat/octo-name-repo/subscription", "commits_url": "https://api.github.com/repos/octocat/octo-name-repo/commits{/sha}", "git_commits_url": "https://api.github.com/repos/octocat/octo-name-repo/git/commits{/sha}", "comments_url": "https://api.github.com/repos/octocat/octo-name-repo/comments{/number}", "issue_comment_url": "https://api.github.com/repos/octocat/octo-name-repo/issues/comments{/number}", "contents_url": "https://api.github.com/repos/octocat/octo-name-repo/contents/{+path}", "compare_url": "https://api.github.com/repos/octocat/octo-name-repo/compare/{base}...{head}", "merges_url": "https://api.github.com/repos/octocat/octo-name-repo/merges", "archive_url": "https://api.github.com/repos/octocat/octo-name-repo/{archive_format}{/ref}", "downloads_url": "https://api.github.com/repos/octocat/octo-name-repo/downloads", "issues_url": "https://api.github.com/repos/octocat/octo-name-repo/issues{/number}", "pulls_url": "https://api.github.com/repos/octocat/octo-name-repo/pulls{/number}", "milestones_url": "https://api.github.com/repos/octocat/octo-name-repo/milestones{/number}", "notifications_url": "https://api.github.com/repos/octocat/octo-name-repo/notifications{?since,all,participating}", "labels_url": "https://api.github.com/repos/octocat/octo-name-repo/labels{/name}", "releases_url": "https://api.github.com/repos/octocat/octo-name-repo/releases{/id}", "deployments_url": "https://api.github.com/repos/octocat/octo-name-repo/deployments" }, "html_url": "https://github.com/octocat/octo-name-repo/packages/40201" }`

## [Delete a package for a user](#delete-a-package-for-a-user)

Deletes an entire package for a user. You cannot delete a public package if any version of the package has more than 5,000 downloads. In this scenario, contact GitHub support for further assistance.

If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `delete:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Delete a package for a user"](#delete-a-package-for-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Delete a package for a user"](#delete-a-package-for-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `username` string Required  The handle for the GitHub user account. |

### [HTTP response status codes for "Delete a package for a user"](#delete-a-package-for-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Delete a package for a user"](#delete-a-package-for-a-user--code-samples)

#### Request example

delete/users/{username}/packages/{package\_type}/{package\_name}

Copy to clipboard curl request example

`curl -L \ -X DELETE \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/packages/PACKAGE_TYPE/PACKAGE_NAME`

Response

`Status: 204`

## [Restore a package for a user](#restore-a-package-for-a-user)

Restores an entire package for a user.

You can restore a deleted package under the following conditions:

* The package was deleted within the last 30 days.
* The same package namespace and version is still available and not reused for a new package. If the same package namespace is not available, you will not be able to restore your package. In this scenario, to restore the deleted package, you must delete the new package that uses the deleted package's namespace first.

If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `write:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Restore a package for a user"](#restore-a-package-for-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Restore a package for a user"](#restore-a-package-for-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `username` string Required  The handle for the GitHub user account. |

Query parameters

| Name, Type, Description |
| `token` string  package token |

### [HTTP response status codes for "Restore a package for a user"](#restore-a-package-for-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Restore a package for a user"](#restore-a-package-for-a-user--code-samples)

#### Request example

post/users/{username}/packages/{package\_type}/{package\_name}/restore

Copy to clipboard curl request example

`curl -L \ -X POST \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/packages/PACKAGE_TYPE/PACKAGE_NAME/restore`

Response

`Status: 204`

## [List package versions for a package owned by a user](#list-package-versions-for-a-package-owned-by-a-user)

Lists package versions for a public package owned by a specified user.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "List package versions for a package owned by a user"](#list-package-versions-for-a-package-owned-by-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "List package versions for a package owned by a user"](#list-package-versions-for-a-package-owned-by-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `username` string Required  The handle for the GitHub user account. |

### [HTTP response status codes for "List package versions for a package owned by a user"](#list-package-versions-for-a-package-owned-by-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "List package versions for a package owned by a user"](#list-package-versions-for-a-package-owned-by-a-user--code-samples)

#### Request example

get/users/{username}/packages/{package\_type}/{package\_name}/versions

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/packages/PACKAGE_TYPE/PACKAGE_NAME/versions`

Response

`Status: 200`

`[ { "id": 3497268, "name": "0.3.0", "url": "https://api.github.com/users/octocat/packages/rubygems/octo-name/versions/3497268", "package_html_url": "https://github.com/octocat/octo-name-repo/packages/40201", "license": "MIT", "created_at": "2020-08-31T15:22:11Z", "updated_at": "2020-08-31T15:22:12Z", "description": "Project for octocats", "html_url": "https://github.com/octocat/octo-name-repo/packages/40201?version=0.3.0", "metadata": { "package_type": "rubygems" } }, { "id": 387039, "name": "0.2.0", "url": "https://api.github.com/users/octocat/packages/rubygems/octo-name/versions/387039", "package_html_url": "https://github.com/octocat/octo-name-repo/packages/40201", "license": "MIT", "created_at": "2019-12-01T20:49:29Z", "updated_at": "2019-12-01T20:49:30Z", "description": "Project for octocats", "html_url": "https://github.com/octocat/octo-name-repo/packages/40201?version=0.2.0", "metadata": { "package_type": "rubygems" } }, { "id": 169770, "name": "0.1.0", "url": "https://api.github.com/users/octocat/packages/rubygems/octo-name/versions/169770", "package_html_url": "https://github.com/octocat/octo-name-repo/packages/40201", "license": "MIT", "created_at": "2019-10-20T14:17:14Z", "updated_at": "2019-10-20T14:17:15Z", "html_url": "https://github.com/octocat/octo-name-repo/packages/40201?version=0.1.0", "metadata": { "package_type": "rubygems" } } ]`

## [Get a package version for a user](#get-a-package-version-for-a-user)

Gets a specific package version for a public package owned by a specified user.

OAuth app tokens and personal access tokens (classic) need the `read:packages` scope to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Get a package version for a user"](#get-a-package-version-for-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)
* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Get a package version for a user"](#get-a-package-version-for-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `package_version_id` integer Required  Unique identifier of the package version. |
| `username` string Required  The handle for the GitHub user account. |

### [HTTP response status codes for "Get a package version for a user"](#get-a-package-version-for-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `200` | OK |

### [Code samples for "Get a package version for a user"](#get-a-package-version-for-a-user--code-samples)

#### Request example

get/users/{username}/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}

Copy to clipboard curl request example

`curl -L \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID`

Response

`Status: 200`

`{ "id": 387039, "name": "0.2.0", "url": "https://api.github.com/users/octocat/packages/rubygems/octo-name/versions/387039", "package_html_url": "https://github.com/octocat/octo-name-repo/packages/40201", "license": "MIT", "created_at": "2019-12-01T20:49:29Z", "updated_at": "2019-12-01T20:49:30Z", "description": "Octo-name client for Ruby", "html_url": "https://github.com/octocat/octo-name-repo/packages/40201?version=0.2.0", "metadata": { "package_type": "rubygems" } }`

## [Delete package version for a user](#delete-package-version-for-a-user)

Deletes a specific package version for a user. If the package is public and the package version has more than 5,000 downloads, you cannot delete the package version. In this scenario, contact GitHub support for further assistance.

If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `delete:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Delete package version for a user"](#delete-package-version-for-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Delete package version for a user"](#delete-package-version-for-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `username` string Required  The handle for the GitHub user account. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Delete package version for a user"](#delete-package-version-for-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Delete package version for a user"](#delete-package-version-for-a-user--code-samples)

#### Request example

delete/users/{username}/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}

Copy to clipboard curl request example

`curl -L \ -X DELETE \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID`

Response

`Status: 204`

## [Restore package version for a user](#restore-package-version-for-a-user)

Restores a specific package version for a user.

You can restore a deleted package under the following conditions:

* The package was deleted within the last 30 days.
* The same package namespace and version is still available and not reused for a new package. If the same package namespace is not available, you will not be able to restore your package. In this scenario, to restore the deleted package, you must delete the new package that uses the deleted package's namespace first.

If the `package_type` belongs to a GitHub Packages registry that supports granular permissions, the authenticated user must have admin permissions to the package. For the list of these registries, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#granular-permissions-for-userorganization-scoped-packages)."

OAuth app tokens and personal access tokens (classic) need the `read:packages` and `write:packages` scopes to use this endpoint. For more information, see "[About permissions for GitHub Packages](https://docs.github.com/packages/learn-github-packages/about-permissions-for-github-packages#permissions-for-repository-scoped-packages)."

### [Fine-grained access tokens for "Restore package version for a user"](#restore-package-version-for-a-user--fine-grained-access-tokens)

This endpoint works with the following fine-grained token types:

* [GitHub App installation access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

The fine-grained token does not require any permissions.

### [Parameters for "Restore package version for a user"](#restore-package-version-for-a-user--parameters)

Headers

| Name, Type, Description |
| `accept` string  Setting to `application/vnd.github+json` is recommended. |

Path parameters

| Name, Type, Description |
| `package_type` string Required  The type of supported package. Packages in GitHub's Gradle registry have the type `maven`. Docker images pushed to GitHub's Container registry (`ghcr.io`) have the type `container`. You can use the type `docker` to find images that were pushed to GitHub's Docker registry (`docker.pkg.github.com`), even if these have now been migrated to the Container registry.  Can be one of: `npm`, `maven`, `rubygems`, `docker`, `nuget`, `container` |
| `package_name` string Required  The name of the package. |
| `username` string Required  The handle for the GitHub user account. |
| `package_version_id` integer Required  Unique identifier of the package version. |

### [HTTP response status codes for "Restore package version for a user"](#restore-package-version-for-a-user--status-codes)

| Status code | Description |
| --- | --- |
| `204` | No Content |
| `401` | Requires authentication |
| `403` | Forbidden |
| `404` | Resource not found |

### [Code samples for "Restore package version for a user"](#restore-package-version-for-a-user--code-samples)

#### Request example

post/users/{username}/packages/{package\_type}/{package\_name}/versions/{package\_version\_id}/restore

Copy to clipboard curl request example

`curl -L \ -X POST \ -H "Accept: application/vnd.github+json" \ -H "X-GitHub-Api-Version: 2026-03-10" \ https://api.github.com/users/USERNAME/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID/restore`

Response

`Status: 204`
