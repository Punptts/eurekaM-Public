uplinks:: [[+ HOME]]
tags:: #type/tool⚙️  #status/boat🚤 

# Set up for Git LFS
---
## Jot down...
#### Steps to set up Git lfs
- **Set up repository in GitHub first**. Follow steps here [[Set up GitHub folder]]

#### ==Set up once per account==
- Make sure that the folder already set up git in it.
- Open terminal/iterms on your Mac
- Run ```brew install git-lfs``` (for homebrew user)
- Then, verify that the installation was successful:
	- Run :  ```git lfs install```
	- The result show :  ```Git LFS initialized```  
---

#### ==Set up per project==
Now, list out all of the types of files you anticipate you will need to track.

```
git lfs track “*.psd”  
git lfs track “*.sketch”  
git lfs track “*.ai”
```

- Then run ``` git add .gitattributes ``` to track mentioned file above.

#### Create First initialize Git lfs
- Commit and push your changes
	- Run : ```git add .``` or ```git add file.psd```
	- Then, ```git commit -m "Add design file"```
	- Finally done! Checkout your GitHub repository.
	- cat .gitmodules - check all path
	- git log - see all commit
	- git dif head (ปัจจุบัน) head^ (ก่อนปัจจุบัน) - to compare

---
## Reference
- https://medium.com/@kellyleigh/using-git-for-design-file-storage-53c59a195094
- **"Git lfs install" does not work** : https://stackoverflow.com/questions/58796472/git-lfs-is-not-a-command-mac-os
