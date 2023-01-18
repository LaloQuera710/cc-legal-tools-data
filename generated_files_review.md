# Generated Files Review


## Overview

There are almost 30,000 files in `docs/` (29,790 as of 2022-01-06). This means
that a comprehensive review of all files changed in a pull request is often
unfeasible (both because of the time required and GitHub's inability to deal
with pull requests with that many files). The instructions below provide a way
to spot check large pull requests by using Docker and emblematic files.

See the [`README.md`](README.md) for additional information on this repository,
the CC Legal Tools namespace, and definitions of terms.


## Review Changes Locally

- The GitHub CLI makes interacting with pull requests locally much easier:
  - [Manual | GitHub CLI][ghcli-manual]
  - [gh pr | Manual | GitHub CLI][ghcli-pr] - Work with GitHub pull requests.
- [Checking out pull requests locally - GitHub Docs][prs-locally] describes how
  to use `git` to checkout a pull request locally

[ghcli-manual]: https://cli.github.com/manual/
[ghcli-pr]: https://cli.github.com/manual/gh_pr
[prs-locally]: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/checking-out-pull-requests-locally


### Emblematic Files

The following files represent the different types of files generated by various
Django views of the [creativecommons/cc-legal-tools-app][cc-legal-tools-app].
The URLs below assume you are running the Docker services, documented below,
for this repository:

| Emblematic Files                           |                                                           |
| ------------------------------------------ | --------------------------------------------------------- |
| **Tool List**                              |                                                           |
| Licenses                                   | https://127.0.0.1:8007/licenses/list                      |
| Public Domain                              | https://127.0.0.1:8007/publicdomain/list                  |
| **Deed**                                   |                                                           |
| CC BY 4.0 English                          | https://127.0.0.1:8007/licenses/by/4.0/deed.en            |
| CC BY-NC-ND 4.0 Arabic (RTL)               | https://127.0.0.1:8007/licenses/by-nc-nd/4.0/deed.ar      |
| CC Sampling+ 1.0 Dutch (retired)           | https://127.0.0.1:8007/licenses/sampling+/1.0/deed.nl     |
| PDM 1.0 English (no legal code)            | https://127.0.0.1:8007/publicdomain/mark/1.0/deed.en      |
| **Legal Code (Translated)**                |                                                           |
| CC BY 4.0 English                          | https://127.0.0.1:8007/licenses/by/4.0/legalcode.en       |
| CC BY-NC-ND 4.0 Arabic (RTL)               | https://127.0.0.1:8007/licenses/by-nc-nd/4.0/legalcode.ar |
| **Legal Code (Hardcoded)**                 |                                                           |
| CC BY 3.0 Unported English                 | https://127.0.0.1:8007/licenses/by/3.0/legalcode.en       |
| **Legal Code (Import)**                    |                                                           |
| CC BY 3.0 CA English                       | https://127.0.0.1:8007/licenses/by/3.0/ca/legalcode.en    |
| CC BY 3.0 CA French                        | https://127.0.0.1:8007/licenses/by/3.0/ca/legalcode.fr    |
| CC BY-ND 3.0 EG Arabic (RTL)               | https://127.0.0.1:8007/licenses/by-nd/3.0/eg/legalcode.ar |
| CC BY-NC 2.5 Generic (Unported) English    | https://127.0.0.1:8007/licenses/by-nc/2.5/legalcode.en    |
| CC BY-NC-ND 2.0 Generic (Unported) English | https://127.0.0.1:8007/licenses/by-nc-nd/2.0/legalcode.en |
| CC BY-SA 1.0 Generic (Unported) English    | https://127.0.0.1:8007/licenses/by-sa/1.0/legalcode.en    |

[cc-legal-tools-app]: https://github.com/creativecommons/cc-legal-tools-app


### Docker Compose Setup

You can use Docker to locally view the files of a specific branch or pull
request. Note that CC Staff do not use Windows for development and additional
steps may be required on that platform.

1. Install Docker Desktop
   - [Install on Linux | Docker Documentation][installdockerlinux]
   - [Install on Mac | Docker Documentation][installdockermac]
   - [Install on Windows | Docker Documentation][installdockerwindows]
3. Ensure you are the top level of directory of this repository (where the
   `docker-compose.yml` file is)
4. Build the containers
    ```shell
    docker compose build
    ```
5. **Run the containers**
    ```shell
    docker compose up
    ```
   - **static** ([127.0.0.1:8007](http://127.0.0.1:8007/)): a static web
     server serving the `docs/` directory

[installdockerlinux]: https://docs.docker.com/desktop/install/linux-install/
[installdockermac]: https://docs.docker.com/desktop/install/mac-install/
[installdockerwindows]: https://docs.docker.com/desktop/install/windows-install/