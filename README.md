# Git-tip
Git 사용 시 발생한 오류 해결법들


## push, pull 오류 
git remote add origin <repo url>을 통해 로컬 저장소와 원격 저장소를 연동하고 commit 한 후에 git push로 commit 내용을 원격 저장소로 옮기려고 하면 오류가 난다.  

이때 나는 오류는 원격 저장소에 있는 Readme.md 가 로컬 저장소에는 존재하지 않기 때문에 생기는 오류이다.  

따라서 원격 저장소의 내용을 pull해서 Readmd.md를 로컬 저장소로 끌어온 후 다시 push를 시도해야 한다.  

그런데 git pull 하려고 했더니 또 오류가 난다.  

There is no tracking information for the current branch.
Please specify which branch you want to merge with.

위와 같은 오류가 나는데 이것은 **git pull --allow-unrelated-histories origin main** 을 입력해 줌으로써 해결이 가능하다.  

그러고 나서 git push 를 하려 하면 또 The current branch main has no upstream branch.To push the current branch and set the remote as upstream 이런 오류가 나는데 이것은   
**git push --set-upstream origin main** 을 입력하여 해결한다.  

이거 다 한 후에 git push 하면 정상적으로 push 됨.
