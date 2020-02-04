# Buffer Overflow

## Linux

#### 

## Windows

### Immunity Debugger

#### Get modules information

```text
!mona
```

## Useful commands

### Generate debruijn/cyclic pattern

```text
ragg2 -P 100 -r
```

### Find pattern offset

```text
ragg2 -q 0x42414141
```

### Assemble code

```text
rasm2 -a x86 -C 'add esp, -1500'
```

## References

* [https://www.corelan.be/index.php/2009/07/19/exploit-writing-tutorial-part-1-stack-based-overflows/](https://www.corelan.be/index.php/2009/07/19/exploit-writing-tutorial-part-1-stack-based-overflows/)

