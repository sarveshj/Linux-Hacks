

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

### ```[14] Pytorch enable GPU/CPU based on availability```

```python
device = torch.device("cuda:0" if torch.cuda_is_available() else "cpu")
```

### ```[15] Pytorch choose GPU based on availability```

Option 1:
```python
os.system("export CUDA_VISIBLE_DEVICES = 0,1")
```


Option 2: Using bash commandline
```bash
export CUDA_VISIBLE_DEVICES = 0,1
```


