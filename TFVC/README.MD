# Team Foundation Version Control (TFVC) and Git  

# Azure DevOps TFVC vs Git - Keyword Comparison

| Feature/Concept | TFVC                      | Git                           |
|-----------------|---------------------------|-------------------------------|
| **Repository**  | Team Project Collection   | Repository or Repo            |
| **Branch**      | Branch                    | Branch                        |
| **Check-out**   | Check-out                 | Check-out                    |
| **Check-in**    | Check-in                  | Commit                        |
| **Changeset**   | Changeset                 | Commit                        |
| **History**     | Changeset history         | Commit history                |
| **Merge**       | Merge                     | Merge                         |
| **Conflict**    | Merge conflict            | Merge conflict                |
| **Lock**        | Exclusive lock            | No lock (concurrent editing)  |
| **Clone**       | Get latest version        | Clone                         |
| **Pull**        | Get latest version        | Pull                          |
| **Push**        | Check-in (with pending changes) | Push                     |
| **Pull Request**| Shelve Set                | Pull Request                  |
| **Remote**      | N/A                       | Remote                        |
| **Fetch**       | N/A                       | Fetch                         |
| **Commit ID**   | Changeset ID              | Commit ID (SHA-1 hash)        |
| **Tag**         | Label                     | Tag                           |
| **Repository URL**| Repository URL           | Repository URL                |
| **Fork**        | N/A                       | Fork                          |
| **Stash**       | Shelve changes            | Stash changes                 |


## Azure DevOps TFVC vs Git  

| Feature                      | TFVC                                    | Git                                        |
|------------------------------|-----------------------------------------|--------------------------------------------|
| **Type of Version Control**  | Centralized                             | Distributed                                |
| **Branching and Merging**    | More rigid, can be complex              | Lightweight, more flexible                 |
| **Check-out/Check-in**       | Files checked out with lock             | No lock required, concurrent work allowed |
| **History Tracking**         | Changesets                              | Commits                                    |
| **File System**              | Exclusive file locking                  | No exclusive file locking                  |
| **Workflow Flexibility**     | Less flexible, more linear              | Highly flexible, supports various workflows |
| **Collaboration**            | Less suitable for distributed teams     | Excellent for distributed teams            |
| **Performance with Large Binary Files** | Handles large files better      | Not as efficient with large files          |
| **Learning Curve**           | Easier for centralized VC users         | Steeper, especially for new users          |
| **Offline Work**             | Requires server connection              | Supports extensive offline work            |
| **Repository Size**          | Handles large repositories well         | Repository size can become an issue        |
| **Branching Complexity**     | More complex                            | Simplified                                 |
| **Merge Conflicts**          | Fewer automatic resolutions            | Better support for resolving conflicts     |
| **History Examination**      | Tracks changesets and work items        | Granular tracking at the commit level      |
| **Tooling Integration**      | Integrates well with Microsoft tools    | Integrates with various tools              |
| **Open Source Projects**     | Less common                             | Widely used                                |

