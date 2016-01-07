---
layout: post
title: Google Protocol Buffer
tags: default
---
**简介**
*什么是Google Protocol Buffer？*

> Google Protocol Buffer( 简称 Protobuf) 是 Google 公司内部的混合语言数据标准，目前已经正在使用的有超过 48,162 种报文格式定义和超过 12,183 个 .proto 文件。他们用于 RPC 系统和持续数据存储系统。

> Protocol Buffers 是一种轻便高效的结构化数据存储格式，可以用于结构化数据串行化，很适合做数据存储或 RPC 数据交换格式。它可用于通讯协议、数据存储等领域的语言无关、平台无关、可扩展的序列化结构数据格式。目前提供了 C++、Java、Python 三种语言的 API。


笔者心得：在一个go项目中，protobuf即保证了通讯过程中存储格式的完整性（一般情况下，*.pb.go不人为直接修改），在redis灌库存储的过程中，也大大节约了宝贵的内存空间（融合了golang的优势）。源代码请见[protobuf github](https://github.com/google/protobuf)。


----------

**安装**：
以下命令行，简单无脑：

    wget https://github.com/google/protobuf/releases/download/v2.6.1/protobuf-2.6.1.tar.gz
    tar zxvf protobuf-2.6.1.tar.gz
    cd protobuf-2.6.1
    ./configure
    make
    make install
    protoc   -h

----------

**举例**：
 1. 创建一个*.proto文件。
 2. 通过--go_out使用go protobuf提供的Protobuf编译器protoc-gen-go。

    protoc --go_out=. *.proto

这时会生成一个名为 *.pb.go 的源文件。

