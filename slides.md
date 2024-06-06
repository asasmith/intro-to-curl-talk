---
theme: seriph
background: https://images.unsplash.com/photo-1644225797166-db7bba6f8a95?q=80&w=1000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  A Brief Intro to cURL
transition: slide-left
title: A Brief Intro to cURL
mdc: true
monaco: true
monacoTypesSource: local # or cdn or none
---

# A Brief Intro to cURL

---
layout: center
---

<h1 class="text-center">Asa Smith</h1>

<a v-click src="https://github.com/asasmith">@asasmith on github</a>
<span v-click> (one million incomplete side projects and learning adventures)</span>
    
<a v-click src="https://twitter.com/average_dev_asa">@average_dev_asa on 🐦</a>
<span v-click> (literally 10's of tweets per year)</span>


<style>
    a {
        border-bottom: none !important;
        border-style: none !important;
        color: rgb(251, 251, 254) !important;
    }
</style>
---
layout: center
class: text-center
---

# What is cURL?

## <v-click>client </v-click><v-click>URL</v-click>

<div class="flex flex-col justify-center">
<v-click>
 - A command-line tool and library for transferring data with URLs
</v-click>
<v-click>
 - Free and open source since 1998
</v-click>
<v-click>
 - Available on every os
</v-click>
</div>

<!-- curl stands for client url -->
---
layout: center
class: text-center
---
# cURL supports...
<v-click>DICT, </v-click>
<v-click>FILE, </v-click>
<v-click>FTP, </v-click>
<v-click>FTPS, </v-click>
<v-click>GOPHER, </v-click>
<v-click>GOPHERS, </v-click>
<v-click>HTTP, </v-click>
<v-click>HTTPS, </v-click>
<v-click>IMAP, </v-click>
<v-click>IMAPS, </v-click>
<v-click>LDAP, </v-click>
<v-click>LDAPS, </v-click>
<v-click>MQTT, </v-click>
<v-click>POP3, </v-click>
<v-click>POP3S, </v-click>
<v-click>RTMP, </v-click>
<v-click>RTMPS, </v-click>
<v-click>RTSP, </v-click>
<v-click>SCP, </v-click>
<v-click>SFTP, </v-click>
<v-click>SMB, </v-click>
<v-click>SMBS, </v-click>
<v-click>SMTP, </v-click>
<v-click>SMTPS, </v-click>
<v-click>TELNET, </v-click>
<v-click>TFTP, </v-click>
<v-click>WS and WSS. curl supports TLS certificates, </v-click>
<v-click>HTTP POST, </v-click>
<v-click>HTTP PUT, </v-click>
<v-click>FTP uploading, </v-click>
<v-click>HTTP form based upload, </v-click>
<v-click>proxies (SOCKS4, SOCKS5, HTTP and HTTPS), </v-click>
<v-click>HTTP/2, </v-click>
<v-click>HTTP/3, </v-click>
<v-click>cookies, </v-click>
<v-click>user+password authentication (Basic, Plain, Digest, CRAM-MD5, SCRAM-SHA, NTLM, Negotiate, Kerberos, Bearer tokens and AWS Sigv4), </v-click>
<v-click>file transfer resume, </v-click>
<v-click>proxy tunneling, </v-click>
<v-click>HSTS, </v-click>
<v-click>Alt-Svc, </v-click>
<v-click>unix domain sockets, </v-click>
<v-click>HTTP compression (gzip, brotli and zstd), </v-click>
<v-click>etags, </v-click>
<v-click>parallel transfers, </v-click>
<v-click>DNS-over-HTTPS </v-click>
<v-click>and more.</v-click>

---
layout: center
class: text-center
---

# um, ok, but y tho

<v-click>
You've probably come a across something like this before
</v-click>

<v-click>
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
</v-click>

<p v-click>
and since nothing bad has ever happened from downloading things on the internet
</p v-click>

<p v-click>
copy and paste FTW 🍾
</p v-click>

---
layout: center
class: text-center
---

# But what if you actually knew what that command did?

<div v-click class="flex justify-center">
    <iframe src="https://giphy.com/embed/3o7btNhMBytxAM6YBa" width="480" height="268" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
</div>

---
layout: center
---

# Anatomy of a cURL command

<v-click>
```bash
curl [options] [url]
```
</v-click>

---
layout: center
---

<div class="text-center">
    <h1>Example</h1>
</div>

```bash{1|3|3-4|3-5|7-8|all}
curl -o outputFile.html http://example.com

# [options]
# -o (aliases -O, -output)
# The cURL command generates an output and this specifies the filename to write the output to (outputFile.html)

# [url]
# http://example.com
```

---
layout: center
class: text-center
---

<h1 class="text-center">The NVM install command from earlier</h1>

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

<p class="text-left" v-click>
    [options]
    <br>
    -o-: The -o command writes the output to a file name but when an extra - is added the output is written to standard out (stdout)
</p v-click>

<p class="text-left" v-click>
    [url]
    <br>
    https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh
</p v-click>

<p class="text-left" v-click>
    | (pipe operator) This is the pipe operator in shell commands.
    <br>
    It takes the output of the command on its left (in this case, the output of the curl command) and uses it as the input for the command on its right.
</p v-click>

<p class="text-left" v-click>
    bash (shell command)
    <br>
    This part of the command invokes the Bash shell to execute the input it receives from the pipe.
    Since the input is the script downloaded by curl, this effectively means the script is executed by Bash.
</p v-click>

---
layout: center
---

# Ok, cool. But I use Homebrew to download everything

<div v-click class="flex justify-center">
    <iframe src="https://giphy.com/embed/9V1F9o1pBjsxFzHzBr" width="480" height="268" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
</div>

---
layout: center
---

<h1 class="text-center">HTTP/S requests</h1>


```bash{1|3|5|all}
curl -X GET -o yoda.json https://swapi.dev/api/people/20

# -X GET: sets request method GET

# -o: Write results to a file named yoda.json 
```

---
layout: center
---

<div class="flex justify-center">
    <iframe src="https://giphy.com/embed/3ohuAxV0DfcLTxVh6w" width="480" height="268" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
</div>

---
layout: center
---

```bash{all|1-2|1-4|1-6|1-7|all}
curl
    -X POST
    # -H: add a header to the request
    -H "Content-Type: application/json"
    # -d: data to be sent with the request
    -d '{ "title": "A Brief Intro to cURL", "body": "We all know about cURL now!", "userId": 42 }'
    -o response.json
    https://jsonplaceholder.typicode.com/posts
```

<v-click>
```json
// response.json

{
  "title": "A Brief Intro to cURL",
  "body": "We all know about cURL now!",
  "userId": 42,
  "id": 101
}
```
</v-click>

---
layout: center
class: text-center
---

# But I can do all of this with Postman/Insomnia/etc

<p v-click>Sometimes weird things happen</p>
<h2 v-click>When in doubt, cURL it out™</h2>
<p v-click>Sometimes it's good to know how the tools we use regularly actually work</p>
<p v-click>Sometimes you want to brag about something other than using Vim</p>
<p v-click>I use Vim btw</p>

---
layout: center
---

<h1 class="text-center">Resources</h1>

- [cURL](https://curl.se/)
- [Mastering the cURL command line ("A more than three hours deep dive video tutoral in how to use and make the best of curl on the command line")](https://www.youtube.com/watch?v=V5vZWHP-RqU)

<style>
    a {
        border-bottom: none !important;
        border-style: none !important;
        color: rgb(251, 251, 254) !important;
    }
</style>
