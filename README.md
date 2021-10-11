

### ``` [1] Compress PDF (Source: Stack Overflow) ```


#### 1a using postscript as Intermediate step 

#### Step 1:Convert to intermediate postscript format
`pdf2ps large.pdf large.ps`


#### Step2 Convert ps back to pdf
`ps2pdf large.ps small.pdf`


#### 1b Using ghostscript


`gs -dQUIET -dBATCH -dNOPAUSE -sDEVICE=pdfwrite -dPDFSETTINGS=/printer    -sOutputFile=output.pdf Sarvesh_BOB_filled_scanned_final.pdf`



### ``` [2] Run a Bash command every 10 seconds ```

Syntax
#### ```watch -n10 "args command"```

Example - Command to list files in the current directory
#### Example: watch -n10 "ls -ltr | wc"




### ``` [3] Convert all files in a folder - Example Convert files between jpg and png ```

```
for i in *.jpg ; 
  do 
    convert "$i" "${i%.*}.png" ; 
    
    
  done
```




### ``` [4] Set bash prompt                           ```

```export PS1= "\u@\h: \w:$"```

where ```\u ``` is username,
      ```\h ``` is hostname,
      ```\w ``` is present working directory
      
      
example: ```export PS1="$(whoami)@$(hostname):$(pwd)" ```
      


### ``` [5] Search for files with multiple extensions - example: Images with both `.png` and `.jpg` format ```

``` find <file_path> -iname "*.jpg" -or -iname "*.png" | wc ```


### ```[6] Copy files from remote machine to local machine with following symbolic option```

``` rsync -avzL username@remote:path local-path ```



### ```[7] Changing jupyter notebook themes ```

Install jupyterthemes and run the following command for monokai font
```jt -t monokai -cellw 90% ```


For list of all available themes use ```jt -l```



### ```[8] Checking Webcam available and ready for use ```

#### **Checking  if webcam detected by Ubuntu**

- Use this command `lsusb` to list all devices detected


### **Take test photos/video using Cheese**

- Go to terminal, type `cheese` and a window should pop-up. You can take phots(single/burst) and record video!
- In case cheese is not installed, you can install it using `sudo apt-get install cheese`


### ```[9] Download large zip files from dropbox link```

- `wget <url>`
- Check integrity of zip file using `unzip -t <zipfile_name>`


### ```[10] Read Image and overlay rectangle using Python```

```python
from matplotlib import pyplot as plt
from PIL import Image
from matplotlib.patches import Rectangle

image = Image.open(<path_to_img>)
# rectangle co-ordinates is of the form (xmin,ymin), width, height
origin = (xmin, ymin)
width  = xmax-xmin
height = ymax-ymin

# display image and overlay rectangle
plt.imshow(image)
patch = Rectangle(origin, width, height, linewidth = 10, edgecolor='r')
plt.gca().add_patch(patch)
plt.show()

```

### ```[11] Get Laptop configuration from command line```

- `sudo lshw -html > config.html` to dump specification as html file
- Use `firefox config.html` to view the details


### ```[12] Git stop tracking a file```

```bash
git update-index --skip-worktree <file_name>
```

### ```[13] Saving and recreating a conda virtual environment ```
```bash


# activate conda environment
conda activate <env_name>

# export environment to a file
conda env export  > environment.yml

# recreate conda environment from file
conda env create -f environment.yml


```


### Git and GitLab command lines

- Useful references: ~ [Gitlab doc for commandline usage] (https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html)
- Tip for better understanding: Make changes in command line and view in Gitlab repo!

#### step 1: Generate SSH Key Pair
ssh-keygen

### modify ssh config and change permissions
 - add the following to ~/.ssh/config (SSH config file)
  ```
   User git
     Hostname gitlab.com
     IdentityFile ~/.ssh/id_<file_name>
     TCPKeepAlive yes
     IdentitiesOnly yes
  ```

- change file ownership and permissions
```
chown $USER  ~/.ssh/config
chmod 600 ~/.ssh/config
```


### check ssh permissions
```bash 
ssh -vv git@gitlab.com
```
should get the response if all is good

```PTY allocation request failed on channel 0
Welcome to GitLab, @sarveshj!
Connection to gitlab.com closed.
```


### Set local(repo specific)/Global user name




and you can verify your config settings using ``` git config --list ```


### Set Origin/Master for this repo
``` git remote add origin git@gitlab.com:sarveshj/linkedin_demo.git ```
which can be checked using

```git remote -v```

### Get latest code -- branching

Get branch name using ```git branch --list```


Use ```git pull -all``` for all branches
Use ```git pull origin main``` for specific branch



For **existing** branch
git pull remote <branch_name> Ex: ```git pull remote main```

Checkout the code for **new** branch/ Create a new feature branc
```git checkout -b <branch_name>``` Ex: ```git checkout -b sarvesh_scratch```

### Additional Useful Branch commands

- Switch branches using ```git checkout <branch_name> ``` Ex: ```git checkout main ``  
- Check current branch you're on using ```git status```
- 
`
### Push changes to remote repo

Let `test.py` be the file to be pushed

1. Navigate to branch of choice using ```git checkout branch```
2. Make changes and save it
3. check if the changes are saved using ```git status```
4. Stage the files for commit using ```git add test.py```
5. Commit the file to local repo with a custom message ```git commit -m "added new lines" ```
6. Push to spefic branch say sarvesh_branch using ```git push origin <branch_name>```

### Check local repo sync with remote/origin

Run ```git show remote origin``` will show something like in case they are out of sync
```
* remote origin
  Fetch URL: git@gitlab.com:sarveshj/linkedin_demo.git
  Push  URL: git@gitlab.com:sarveshj/linkedin_demo.git
  HEAD branch: main
  Remote branches:
    Sarvesh_scratch_2 tracked
    main              tracked
    sarvesh_scratch   tracked
  Local refs configured for 'git push':
    Sarvesh_scratch_2 pushes to Sarvesh_scratch_2 (up to date)
    main              pushes to main              (local out of date)
    sarvesh_scratch   pushes to sarvesh_scratch   (up to date)



```


### Tips

TODO: tips to handle git merge conflict







