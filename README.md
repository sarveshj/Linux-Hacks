

### ``` [1] Compress PDF using postscript as Intermediate step ```

#### Step 1:Convert to intermediate postscript format
`pdf2ps large.pdf large.ps`


#### Step2 Convert ps back to pdf
`ps2pdf large.ps small.pdf`



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

- wget <url>
- Check integrity of zip file using unzip -t <zipfile_name>



