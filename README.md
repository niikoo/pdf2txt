# pdf2txt
Extract raw text from PDF files 

## Background

pdf2txt is a command line application based on rsc.io/pdf library for parsing PDF files. 

Russ Cox's PDF library has a bug where he ignores any space characters. https://github.com/rsc/pdf/blob/master/page.go#L422

Many folks have sent pull requests to fix the bug, but since the library is no longer used by him, he has chosen to ignore those requests. There might be a reason why he chose to ignore space characters.

It is apparently a very simple bug fix, eliminate the if statement. https://github.com/shakeel/pdf2txt/blob/master/pdf/page.go#L422

I have copied  https://github.com/rsc/pdf/ to this code repo https://github.com/shakeel/pdf2txt/tree/master/pdf

All credit for the PDF library belongs to Russ Cox https://swtch.com/~rsc/ , one of my favorite programmers.

## How to use pdf2txt

### Using go get

1. Install GoLang version 1.14 or above from https://golang.org/dl/ and follow instructions to setup the GoLang development environment.
1. `go get github.com/niikoo/pdf2txt`

### Build From Source

1. Install GoLang version 1.14 or above from https://golang.org/dl/ and follow instructions to setup the GoLang development environment.
1. `mkdir ~/devel`
1. `git clone https://github.com/niikoo/pdf2txt`
1. `cd pdf2txt`
1. `go build`
1. The above step creates `pdf2txt.exe` in the pdf2txt folder. You can copy it anywhere such as `$GOLANG/bin` and ensure that `$GOLANG/bin` is in your PATH.
1. Run `pdf2txt` and specify a PDF file to convert to text.

## Usage

```plaintext
Usage of pdf2txt:

pdf2txt [flags] pdf-file ...

  -out filepath
        filepath for writing output
  -stdout
        Use stdout for output (default) (default true)
  -verbose
        verbose output
```

If you do specify `-out` option as for example `./out`, the text file will be in the `./out` folder, and the filename will be the same as your PDF file with the new file extension `.txt`.

Enjoy!
