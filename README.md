# SELProjet
projet SEL et SEM 

#!/usr/bin/env python

from github import Github
from github import InputGitTreeElement

#enter github username and password
g = Github("Mozer18", "Boueufet18")

#select "SELProjet" repository
repo=g.get_user().get_repo("SELProjet")

t1=repo.get_git_tree("2ffcf3eb0bade1262a87f3008e94f2685af1ea90" , False)

v1 = repo.create_git_blob(content="version 1", encoding="utf-8")
#t1 = repo.create_git_tree(tree=[{"path": "Test.json", "mode": "100644", "type": "blob"}])
c1 = repo.create_git_commit(tree=t1, message="first commit", parents=[])

ref = repo.create_git_ref(ref="master", sha=c1.sha)
#file_Json_URL="./home/mozer/Test.json"
