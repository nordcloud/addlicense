# addlicense

The program ensures source code files have copyright license headers
by scanning directory patterns recursively.

It modifies all source files in place and avoids adding a license header
to any file that already has one.

## install

    go get -u github.com/google/addlicense

## usage

    addlicense [flags] pattern [pattern ...]
   
    -c copyright holder (default "Google LLC")
    -f custom license file (no default)
    -l license type: apache, bsd, mit, mpl (default "apache")
    -y year (defaults to current year)
    -check check only mode: verify presence of license headers and exit with non-zero code if missing    
    -u update mode: if the year in the license was older than current one - update it (eg. 2018 changes to 2018-2021)
    -v verbose mode: print the name of the files that are modified
    
The pattern argument can be provided multiple times, and may also refer
to single files.

## Running in a Docker Container

- Clone the repository using `git clone https://github.com/google/addlicense.git`
- Build your docker container
```bash
docker build -t google/addlicense .
```

- Test the image
```bash
docker run -it google/addlicense -h
```

- Usage example
```bash
docker run -v ${PWD}:/go/src/app/ -it google/addlicense -c "Google LLC" *.go
```

## license

Apache 2.0

This is not an official Google product.
