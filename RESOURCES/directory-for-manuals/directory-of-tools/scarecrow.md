#os/linux/tools/hacking
# ScareCrow

1. 1.
    
    ## 1. Doesn't Required | ScareCrow now requires golang 1.19.1 or later to compile loaders.
    

# Navigate to the Download Directory  
cd ~\Downloads  
# Download the Go-lang linux tar file  
wget https://go.dev/dl/go1.20.5.linux-amd64.tar.gz  
# Remove previous go-files located at /usr/local/go & extracts new file to the same location   
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.20.5.linux-amd64.tar.gz  
# export the path /usr/local/go/bin to the environment variable  
export PATH=$PATH:/usr/local/go/bin  
# Verfiy if everything was successfully  
go version

1. 2.
    
    ## 2. This is Required Instead | Install Go-Lang Packager via apt
    

# └─$ sudo apt install golang-go -y

1. Before you compile ScareCrow, you'll also need to install the dependencies.

### To install any other package, simply:

`go install <package_name>@<version>`

go get github.com/fatih/color  
go get github.com/yeka/zip  
go get github.com/josephspurrier/goversioninfo  
go get github.com/Binject/debug/pe  
go get github.com/awgh/rawreader

Or learn more from ( [https://stackoverflow.com/questions/30295146/how-can-i-install-a-package-with-go-get](https://stackoverflow.com/questions/30295146/how-can-i-install-a-package-with-go-get) )

|Title|github-repo|version of release|go install command|Status|
|---|---|---|---|---|
|Color|https://github.com/fatih/color|v1.15.0|go install github.com/fatih/color@v1.15.0|Installed|
|zip|https://github.com/yeka/zip|latest|go install github.com/yeka/zip@latest|Installed|
||https://github.com/josephspurrier/goversioninfo|v1.4.0|github.com/josephspurrier/goversioninfo@v1.4.0||
||https://github.com/Binject/debug/pe||go install github.com/Binject/debug/pe@latest||
||https://github.com/awgh/rawreader||go install github.com/awgh/rawreader@latest||

1. Make sure that the following are installed on your OS:
    

||Command to Install|Status|
|---|---|---|
|openssl|sudo apt install openssl -y|Installed|
|osslsigncode|sudo apt install osslsigncode -y|Installed|
|mingw-w64|sudo apt install mingw-w64 -y|Installed|

1. Then to the directory where you have cloned the reposiroty & build it using ‘sudo’ priviledge

`sudo go build ScareCrow.go`

1. You'll get a new File named [ [ScareCrow](without extension. in the same directory where the file is located. type the below command

`./ScareCrow -h`