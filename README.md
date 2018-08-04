# gitlab-transfer
transfer reciclanet's github repos to new account in gitlab
git remote add github https://yourLogin@github.com/yourLogin/yourRepoName.git
git push --mirror github



I was able to fully export my project along with all commits, branches and tags to gitlab via following commands run locally on my computer:

    To illustrate my example, I will be using https://github.com/raveren/kint as the source repository that I want to import into gitlab. I created an empty project named Kint (under namespace raveren) in gitlab beforehand and it told me the http git url of the newly created project there is http://gitlab.example.com/raveren/kint.git

    The commands are OS agnostic.

In a new directory:

git clone --mirror https://github.com/raveren/kint
cd kint.git
git remote add gitlab http://gitlab.example.com/raveren/kint.git
git push gitlab --mirror

Now if you have a locally cloned repository that you want to keep using with the new remote, just run the following commands* there:

git remote remove origin
git remote add origin http://gitlab.example.com/raveren/kint.git
git fetch --all
