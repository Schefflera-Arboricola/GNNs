## Collecting data : 

1. Randomly sampled 1020 developers using GitHub API with the following properties :
     - at least 7 repos with Python as a language
       ```
        from github import Github
        g = Github('github_pat_token')
        query = 'type:user repos:>7 language:Python'
        developers = g.search_users(query=query)
       ```

2. Then I collected all these developer nodes' features. 
3. Then I went through pinned repositories of all the developers and simultaneously added entries in repositories.csv and edgelist.csv. 
4. In case of forked repos, the parent repo is considered and not the forked repo.
5. API was not able to fetch all the pinned repositories, so those were not included in the repository.csv and edgelist.csv.

<hr>

## Developer nodes

Number of developers: 1020 <br>
Developer features : <br>
'dev_id': unique developer id <br>
'username': username of the developer <br>
'Name': name of the developer <br>
'Bio': the content in the 'Bio' section of the developer <br>
'Company': companies of the developer <br>
'Location': location of the developer <br>
'Public Repositories': number of public repositories  <br>
'Followers': number of followers <br>
'Following': number of following <br>
'listOfPinnedRepos': list of names of pinned repositories of the developer <br>
'starredRepoCount': number of repositories starred by the developer <br>
'yearly_contributions': number of contributions in the last year <br>
'repos_name_list': list of URLs of all the public repositories of the developer <br>
'starred_repos_nameList': list of URLs of all the repositories starred by the developer <br>
'followers_name': list of usernames of all the followers of the developer <br>
'following_names': list of usernames of all the following of the developer <br>
'achievements': list of all the names of achievement badges of the developer <br>
'status': the content of the status section of the developer <br>

<hr>

## Repository nodes

Number of repositories : 2954 <br>
Repository features : <br>
'repo_id': unique repository id <br>
'owner_username': username of the owner of the repository <br>
'repo_name': name of the repository <br>
'description': the content of the 'about' section of the repository <br>
'created_at': date and time of the creation of the repo(`YYYY-MM-DD HH:MM:SS`) <br>
'pushed_at': date and time of the last commit in the repo(`YYYY-MM-DD HH:MM:SS`) <br>
'size': size of repo in KB <br>
'stargazers_count': number of stars <br>
'has_projects': True, if repo has projects, False otherwise <br>
'has_wiki': True, if repo has wiki, False otherwise <br>
'has_pages': True, if repo has pages, False otherwise <br>
'forks_count': number of forks <br>
'open_issues_count': number of open issues <br>
'license': name of the license <br>
'is_template': True, if repo template, False otherwise <br>
'topics': list of topics of the repo <br>
'watching': number of people watching the repo <br>
'contributors_count': number of contributors <br>
'commits_count': number of commits <br>
'languages': list of languages used in the repo <br>
'readme': content of the readme file <br>

<hr>

## Edge list

Number of edges : 3156 <br>
Edge features : <br>
    - isForked : 528 True, 2628 False <br>
    - isTopContributor : 2916 True, 216 False, 24 NA <br>
    - repo_id <br>
    - dev_id <br>


## Graph properties :

Number of nodes: 3974 <br>
Number of edges: 3153 <br>
Type : Heterogeneous Bipartite <br>
Average degree: 1.586814292903875 <br>
Graph density: 0.00039939951998587347 <br>
Number of connected components: 899 <br>


## Tools used : 

GitHubAPI, scrape-up library
