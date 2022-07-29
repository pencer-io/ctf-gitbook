# Bash mkdir and cd

Often have to make a folder then cd in to it. Create an alias to do in one go:

```
mkcdir ()
{
    mkdir -p -- "$1" &&
      cd -P -- "$1"
}
```
