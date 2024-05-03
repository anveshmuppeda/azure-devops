# Team Foundation Version Control (TFVC) and Git  

## Azure DevOps TFVC vs Git - Keyword Comparison

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



Here are some common TFVC commands along with examples:

### Get Latest Version:  
Command: tf get   
Example: Get the latest version of all files in the workspace.  
```bash
tf get
```  

### Check Out File:  
Command: tf checkout  
Example: Check out a file for editing.  
```bash
tf checkout myfile.cs
```  

### Check In File:  
Command: tf checkin  
Example: Check in a file with a comment.  
```bash
tf checkin myfile.cs /comment:"Implemented new feature"
```  

###  Undo Check Out:  
Command: tf undo  
Example: Undo checkout of a file.  
```bash
tf undo myfile.cs
```  

## Workspace Operations  
### Create Workspace:  
Command: tf workspace  
Example: Create a new workspace.  
```bash
tf worksace /new MyWorkspace /server:http://tfvc-server:8080/tfs/DefaultCollection
```  

### List Workspaces:  
Command: tf workspaces  
Example: List all workspaces on the server.  
```bash
tf workspaces /server:http://tfvc-server:8080/tfs/DefaultCollection
```  

### Map Workspace:  
Command: tf workfold  
Example: Map a local directory to a server folder in a workspace.  
```bash
tf workfold /map "$/Project" C:\Workspace\Project /server:http://tfvc-server:8080/tfs/DefaultCollection
```

## History and Changesets  
### View History:  
Command: tf history  
Example: View history of a file.  
```bash
tf history myfile.cs
```  

### View Changeset Details:  
Command: tf changeset  
Example: View details of a specific changeset.  
```bash
tf changeset 1234
```  

### Get Specific Version:  
Command: tf get  
Example: Get a specific version of a file.  
```bash
tf get myfile.cs /version:C1234
```  

## Branching and Merging   

### Create Branch:  
Command: tf branch  
Example: Create a branch from a source folder to a target folder.  
```bash
tf branch $/Project/Main $/Project/FeatureBranch /comment:"Created feature branch for new feature"
```  

### Merge Changes:  
Command: tf merge  
Example: Merge changes from one branch to another.  
```bash
tf merge $/Project/FeatureBranch $/Project/Main /recursive /version:T /comment:"Merged feature branch into main"
```  

### Resolve Merge Conflicts:  
Command: tf resolve  
Example: Resolve merge conflicts in a file.  
```bash
tf resolve myfile.cs /auto:KeepYours
```  

## Miscellaneous  
### Get Latest on Specific Folder:  
Command: tf get  
Example: Get the latest version of files in a specific folder.  
```bash
tf get $/Project/Subfolder
```  

### Label Files:  
Command: tf label  
Example: Label a set of files.  
```bash
tf label MyLabel $/Project/Subfolder /comment:"Labeling files for release"
```  
### View Pending Changes:  
Command: tf status  
Example: View pending changes in the workspace.  
```bash
tf status
```  
These commands should give you a good starting point for using TFVC in Azure DevOps. Make sure to replace placeholders like myfile.cs and $\Project with your actual file and project names.  