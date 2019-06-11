

## ``` [1] Compress PDF using postscript as Intermediate step ```

#### Step 1:Convert to intermediate postscript format
`pdf2ps large.pdf large.ps`


#### Step2 Convert ps back to pdf
`ps2pdf large.ps small.pdf`



## ``` [2] Run a Bash command every 10 seconds ```

Syntax
#### ```watch -n10 "args command"```

Example - Command to list files in the current directory
#### Example: watch -n10 "ls -ltr | wc"




## ``` [3] Convert all files in a folder - Example Convert files between jpg and png ```
for i in *.jpg ; 
  do 
    convert "$i" "${i%.*}.png" ; 
  done
```




# References

[1] Stackoverflow pdf compression  
https://stackoverflow.com/questions/5296667/pdftk-compression-option

[2] Excecute Bash Command every 10 seconds  
https://askubuntu.com/questions/82616/how-to-execute-command-every-10-seconds-without-cron

