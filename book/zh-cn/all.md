---
weight: 5003
title: "附录A：源码文件分配索引及完成情况"
---

# 附录A：源码文件分配索引及完成情况

TODO: 等全书写完后，重新组织本附录

下面列出了 Go 源码文件所实现的功能，以及他们主要功能的介绍，在本书正文中对应的（粗略）位置：

## 第 5 章 Go 程序生命周期

boot:

- [x] src/cmd/go
- [x] src/cmd/internal/compile
- [x] src/internal/cpu
- [x] src/runtime
  - [x] rt0_darwin_amd64.s
  - [x] rt0_js_wasm.s
  - [x] rt0_linux_amd64.s
  - [x] runtime1.go
  - [x] os_darwin.go 
  - [x] os_linux.go
  - [x] go_tls.h

## 第 6 章 调度器

sched, runtime sync:

- [x] src/os
  - [x] /signal
- [x] src/runtime
  - [x] sched
    - [x] runtime.go
    - [x] runtime2.go
    - [x] proc.go
    - [x] stack.go
  - [x] signal
    - [x] os_linux_generic.go
    - [x] sigaction.go
    - [x] signal_amd64x.go
    - [x] signal_darwin.go
    - [x] signal_darwin_amd64.go
    - [x] signal_linux_amd64.go
    - [x] signal_unix.go
    - [x] sigqueue.go
    - [x] sigtab_linux_generic.go
  - [x] sync
    - [x] sema.go
    - [x] lock_futex.go
    - [x] lock_js.go
    - [x] lock_sema.go
    - [ ] rwmutex.go
- [ ] src/net
- [x] src/time
- [ ] src/runtime
  - [ ] net
    - [ ] netpoll.go
    - [ ] netpoll_epoll.go
    - [ ] netpoll_fake.go
    - [ ] netpoll_kqueue.go
    - [ ] netpoll_stub.go
  - [x] time
    - [x] time.go
    - [x] timestub.go
    - [x] timestub2.go
    - [x] time_fake.go

## 第 7 章 内存分配

allocator:

- [x] src/runtime
  - [x] malloc.go
  - [x] mcache.go
  - [x] mcentral.go
  - [x] mprof.go
  - [x] mfixalloc.go
  - [x] mheap.go
  - [x] mmap.go
  - [x] msize.go
  - [x] mstats.go
  - [x] mkduff.go
  - [x] duff_amd64.s
  - [x] mksizeclasses.go
  - [x] sizeclasses.go
  - [x] mem_darwin.go
  - [x] mem_js.go
  - [x] mem_linux.go
  - [x] memclr_amd64.s
  - [x] memclr_wasm.s
  - [x] memmove_amd64.s
  - [x] memmove_wasm.s
  - [ ] mscavenger.go

## 第 8 章 垃圾回收

GC:

- [ ] src/runtime
  - [ ] mgc.go
  - [ ] mgclarge.go
  - [ ] mgcmark.go
  - [ ] mgcsweep.go
  - [ ] mgcsweepbuf.go
  - [ ] mgcwork.go
  - [ ] mbarrier.go
  - [ ] mwbbuf.go
  - [ ] mbitmap.go
  - [ ] lfstack.go
  - [ ] lfstack_64bit.go
  - [ ] mfinal.go

## 第 9 章 语言核心

runtime type system / keywords:

- [ ] src/go/types
- [ ] src/reflect
- [ ] src/runtime
    - [x] type
      - [x] type.go
      - [x] typekind.go
    - [x] float
      - [x] softfloat64.go
      - [x] float.go
    - [x] chan/select
      - [x] chan.go
      - [x] select.go
    - [x] defer/panic/recover
      - [x] panic.go
    - [ ] map
      - [ ] fastlog2.go
      - [ ] mkfastlog2table.go
      - [ ] fastlog2table.go
      - [ ] alg.go
      - [ ] map.go
      - [ ] map_fast32.go
      - [ ] map_fast64.go
      - [ ] map_faststr.go
      - [ ] hash64.go
      - [ ] heapdump.go
    - [x] interface{}
      - [x] iface.go
    - [ ] slice
      - [ ] slice.go
    - [ ] string
      - [ ] string.go
      - [ ] utf8.go

## 第 10 章 兼容与契约

syscall/cgo:


- [x] src/syscall
- [ ] src/cmd
  - [ ] /cgo
- [ ] src/runtime
  - [ ] /cgo
  - [ ] cgo.go
  - [ ] cgo_mmap.go
  - [ ] cgo_sigaction.go
  - [ ] cgocall.go
  - [ ] cgocallback.go
  - [ ] cgocheck.go
  - [ ] cpuprof.go
  - [ ] textflag.h
  - [ ] funcdata.h
  - [ ] defs_linux_amd64.go
  - [ ] defs_darwin_amd64.go
  - [ ] plugin.go

## 第 11 章 调试组件

race/trace/pprof/msan:

- [ ] src/runtime
  - [ ] profbuf.go
  - [ ] proflabel.go
  - [ ] race.go
  - [ ] race0.go
  - [ ] race_amd64.s
  - [ ] trace.go
  - [ ] traceback.go
  - [ ] debug.go
  - [ ] debugcall.go
  - [ ] msan.go
  - [ ] msan0.go
  - [ ] msan_amd64.s

## 第 12 章 依赖管理


## 第 13 章 编译器

- [x] src/unsafe
- [ ] src/cmd
  - [ ] /compile
  - [ ] /internal/obj

## 第 14 章 链接器


## 第 15 章 同步模式

- [x] src/sync
  - [x] /atomic
    - [x] atomic_pointer
    - [x] internal/atomic
    - [x] internal/sys
  - [x] Map
  - [x] Once
  - [x] Pool
  - [x] WaitGroup
  - [ ] Cond
  - [ ] Mutex
  - [ ] Rwmutex

## 第 16 章 网络操作

## 第 17 章 错误处理

- [x] src/errors
- [x] src/fmt.Errorf

## 第 18 章 泛型与合约

## 通用

  - [x] common
    - [x] asm.s
    - [x] asm_amd64.s
    - [ ] asm_wasm.s
  - [ ] stub
    - [ ] extern.go
    - [ ] symtab.go
    - [ ] cpuflags_amd64.go
    - [ ] cputicks.go
    - [ ] env_posix.go
    - [ ] error.go
    - [ ] print.go
    - [ ] write_err.go
    - [ ] relax_stub.go
    - [ ] stubs.go
    - [ ] stubs2.go
    - [ ] stubs3.go
    - [ ] stubs_linux.go
    - [ ] stubs_nonlinux.go
    - [ ] stubs_x86.go
    - [ ] sys_darwin.go
    - [ ] sys_darwin_amd64.s
    - [ ] sys_linux_amd64.s
    - [ ] sys_wasm.go
    - [ ] sys_wasm.s
    - [ ] sys_x86.go
    - [ ] unaligned1.go

## 许可

[Go under the hood](https://github.com/changkun/go-under-the-hood) | CC-BY-NC-ND 4.0 & MIT &copy; [changkun](https://changkun.de)
