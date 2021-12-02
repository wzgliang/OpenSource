# 偶数科技开源开发实践

## 1. 开发任务介绍

Apache HAWQ是面向企业用户的先进大规模分布式分析型数据库，完整支持SQL规范并提供极其优秀的大数据分析性能表现。其采用了存储与计算分离技术架构，除了吸收了MPP的优点，还具有弹性执行，支持混合工作负载和高扩展性等特性，提供了PB级数据交互式查询能力。HAWQ的开发始于2011年，在基于Greenplum和Postgres多年积累的基础上，成功开发出了适配Hadoop的企业级SQL分析引擎。2018年8月15日，HAWQ正式毕业并成为Apache顶级项目。

通过参加Apache HAWQ的线下实践课程，同学们可以在巩固系统级编程技术的基础上进一步学习大数据处理的相关技术和Apache基金会项目的开发模式。本次课程实践选题分为五大类，同学们可以在和企业导师沟通后组队或者独立选择其中一项。

这些选题分别专注于数据库内核新功能研发；软件开发实践中持续集成支持；国产化适配和软件可移植性提高；可重复的软件性能基准测试；项目历史问题的修复和测试补充。每类选题在贯彻ASF开发模式的前提下分别关注不同的软件开发技术，引导同学们逐步融入Apache HAWQ开发社区，体会开源软件开发的协作模式。

### 1.1 添加新的Apache HAWQ外部表格式支持

> Apache HAWQ当下通过可插拔存储框架支持访问HDFS，但是仅支持ORC格式。为了进一步增加HAWQ访问外部HDFS数据源的功能支持，需要进一步提供不同的常用数据格式的支持。本实践可以利用Apache Arrow项目，需要大量使用C/C++编程。

- TEXT/CSV
- ORC
- Parquet

### 1.2 DevOps集成

> *持续集成*是一种软件开发实践，即团队开发成员经常集成他们的工作，通常每个成员每天至少集成一次，也就意味着每天可能会发生多次集成。每次集成都通过自动化的构建（包括编译，发布，自动化测试）来验证，从而尽早地发现集成错误。
>
> 本实践分类依托于Github Action，需要调试各种配置文件和运维脚本。

- GitHub Action
- 格式化工具和lint检查
- 代码覆盖率报告
- 不同平台的打包工作

### 1.3 可移植性适配

> Apache HAWQ当下仅支持x86_64架构，迁移到国产化平台上需要适配更多的处理器体系结构。
>
> 本实践分类需要对不同工具链调试，需要熟悉系统级编程知识（编译链接运行）。

- ARM
- MIPS

### 1.4 可重复的基准测试评测

> 一般来说，大数据具有3V特性，即Volume（海量）、Velocity（高速）和Variety（多样）。如何客观地比较不同数据管理系统，即大数据测试基准的选择，成为一个重要的研究课题。
>
> 本类实践需要编写可重复的完整测试步骤，方便新用户进行基准性能测试。相应的操作步骤和参考结果需要更新到HAWQ的文档中。

- TPC-H
- TPC-DS
- SSB

### 1.5 功能修复和测试的补充

> 针对HAWQ已存在问题进行修复。

- 测试补充

- 技术文档的修改和编写

- 升级工具

- 元数据版本一致性检查工具
  
  - 升级测试
  
- 导出HAWQ统计信息

  > 用于恢复查询计划

## 2. 任务培养目标

- 熟悉大数据基础软件的原理和使用
- 熟悉Apache社区开发流程
- 熟悉和实践持续集成
- 进行大数据基础软件(Apache HAWQ)的内核开发

## 3. 拟培养人数

实践总人数为6~9人，每2~3人分配一个企业导师，根据选题限制协调组队或者独立开发。

## 4. 企业导师介绍

⌈偶数科技⌋是一家领先的AI和大数据软件提供商，致力于为全球各行业客户提供AI和新一代企业级数据仓库产品，公司的愿景和使命是 “让人类只为兴趣而工作”。 目前⌈偶数科技⌋已经获得⌈红杉中国⌋、⌈红点中国⌋和⌈金山云⌋的三轮投资。 

公司核心产品为新一代云原生数据仓库OushuDB、人工智能系统LittleBoy和数据云平台Lava。OushuDB是新一代云原生数据仓库，也是一个可以原生运行在容器云平台中的并行数据仓库引擎。 LittleBoy是您身边的"人工智能科学家"，帮助你轻松解决一切和人工智能相关的难题。 Lava是一款针对企业用户推出的数据云平台，提供企业用户快速完成数字化转型所需的大数据服务。核心团队来自EMC/Pivotal，IBM，Oracle，Google， Microsoft等著名AI和大数据企业，拥有领先的AI和大数据处理技术，研究成果发表在国际顶级会议中，并拥有多项国际专利。

- 常雷

  > Apache HAWQ数据库顶级项目创始人
  >
  > - 偶数科技创始人
  > - 前EMC高级研究员，组建Greenplum和HAWQ中国数据库团队
  > - 国内外顶级数据管理期刊和会议（如SIGMOD等）发表数篇论文，并拥有多项美国专利
  > - 中国计算机学会数据库专委，中国大数据产业生态联盟专家和中国人工智能百人专家 
  > - 快公司”中国商业最具创意人物100”
  > - 2008年博士毕业于北京大学计算机系

- 陶征霖

  > 偶数科技首席架构师
  >
  > - 负责数据库架构、优化器、执行器等核心模块的研发。
  > - Apache Committer，项目管理委员会PMC成员
  > - 曾服务于Oracle和EMC数据库组，负责数据库存储等核心模块的研发
  > - 毕业于浙江大学计算机系

- 万炽洋

  > 偶数科技核心研发工程师
  >
  > - 本次Apache HAWQ开发实践的内容组织人员
  > - Apache HAWQ committer，有多年大数据基础软件内核开发经验
  > - 负责高性能数据库执行器和云原生存储等核心组件的开发工作
  > - 毕业于北京大学计算机系


- 汪思学

  > 偶数科技核心研发工程师
  >
  > - 负责数据库资源管理器和虚拟计算集群等数据库等核心组件的开发
  > - 毕业于北京大学计算机系
  > - 曾获NOI银牌


## 5. 课程计划

> 包括时间安排3.8--5.31可延长至六月底、课程具体内容、阶段性培养目标。

重规范和原则，轻原理和技术。

每次线上先收集问题，根据问题调整和解决。

前三次暂定周二14:00~16:00和周三16:00~18:00。

### 5.1 Apache HAWQ的编译安装部署以及基本使用

> 成功在机器上编译安装运行HAWQ并运行简单语句。
>
> https://cwiki.apache.org/confluence/display/HAWQ/Build+and+Install
>
> 尝试了一下，这个过程有点过于硬核了。
>
> 4个同学只有1个同学在2H内完成了这个过程。

#### 5.1.1 待办清单

- [ ] Linux/Linux VM/macOS
  - [ ] 最好用macOS或者WSL或者裸机Linux，因为之后要用IDE
  - [ ] 平时千万不要用root用户工作
- [ ] 访问Apache的相关网站
  - [ ] http://hawq.apache.org/
  - [ ] https://cwiki.apache.org/confluence/display/HAWQ
  - [ ] https://issues.apache.org/jira/projects/HAWQ/issues/
  - [ ] https://git.apache.org/repos/asf?p=hawq.git
  - [ ] https://github.com/apache/hawq
- [ ] 订阅HAWQ的邮件列表
  - [ ] mailto:dev-subscribe@hawq.apache.org
  - [ ] mailto:user-subscribe@hawq.apache.org
- [ ] 编译安装HAWQ
- [ ] 安装启动HDFS
- [ ] 启动HAWQ
- [ ] 运行简单的SQL语句
- [ ] github账号
  - [ ] fork from github

#### 5.1.2 问题汇总

- [ ] git clone github很慢？(1.1)

  > 可以用码云的镜像
  > ```bash
  > git clone https://gitee.com/mirrors/hawq
  > ```

- [ ] 工具链没法下载下来（1.2）

  > `source .github/workflows/scripts/toolchain.sh`很慢或者失败。（正常应该是5min结束）
  >
  > 修改`.github/workflows/scripts/toolchain.sh`的`REPO`变量
  >
  > ```bash
  > REPO=http://yumazure.oushu-tech.com:12000/oushurepo/yumrepo/internal/linux/toolchain/
  > ```

- [ ] make的时候出现`cmake_install.cmake:41 (file): file INSTALL cannot copy file`

  > 这是因为缺少安装目录的写权限。
  > ```bash
  > sudo install -o $USER -d /usr/local/hawq
  > ```

- [ ] HDFS安装和启动（2.1）

  ```bash
  wget http://yumazure.oushu-tech.com:12000/oushurepo/yumrepo/internal/linux/toolchain/hadoop-3.3.0.tar.gz
  
  sudo install -o $USER -d /usr/local/hadoop-3.3.0
  sudo ln -snf hadoop-3.3.0 /usr/local/hadoop
  sudo tee /usr/local/bin/hdfs <<<'exec /usr/local/hadoop/bin/hdfs $@'
  sudo chmod a+x /usr/local/bin/hdfs
  tar xf hadoop-3.3.0.tar.gz -C /usr/local/
  
  case $(uname -s) in
    Darwin) .github/workflows/scripts/init_macos.sh ;;
    Linux)  .github/workflows/scripts/init_linux.sh ;;
  esac
  
  export HADOOP_HOME=/usr/local/hadoop
  tee -a $HADOOP_HOME/etc/hadoop/hadoop-env.sh << EOF_hadoop_env
  export JAVA_HOME=$(java -XshowSettings:properties -version 2>&1 | sed -nE 's|.*java.home = (.*
  )|\1|p')
  EOF_hadoop_env
  .github/workflows/scripts/init_hdfs.sh
  ```

- [ ] WSL无法SSH登录

  >  `ssh localhost whoami`失败
  >
  >  ```bash
  >  ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key
  >  sudo service ssh --full-restart
  >  ```

- [ ] hawq init问题（2.2）

  > ```bash
  > case $(uname -s) in
  > Darwin) .github/workflows/scripts/init_macos.sh ;;
  > Linux)  .github/workflows/scripts/init_linux.sh ;;
  > esac
  > 
  > source /usr/local/hawq/greenplum_path.sh
  > .github/workflows/scripts/init_hawq.sh
  > ```

- [ ] make的时候GCC挂了

  > 调整编译的并行度。
  >
  > make -j1

- [ ] vim的使用

  > `:wq`退出。

- [ ] configure失败

  [unrecognized relocation 0x2a in section text](https://stackoverflow.com/questions/52737698/unable-to-compile-unrecognized-relocation-0x2a-in-section-text)

  > ```bash
  > sudo yum install centos-release-scl -y
  > sudo yum install devtoolset-7 -y
  > scl enable devtoolset-7 bash
  > ```

- [ ] macOS HAWQ 初始化失败

  > ```bash
  > 20210317:09:36:21:075743 hawq_init:chiyang:chiyang-[WARNING]:-dyld: Library not loaded: @rpath/libhdfs3.1.dylib
  >   Referenced from: /usr/local/hawq/./bin/gpcheckhdfs
  >   Reason: image not found
  > 20210317:09:36:21:075743 hawq_init:chiyang:chiyang-[ERROR]:-Check hdfs failed, please verify your hdfs settings
  > ```
  >
  > ```bash
  > install_name_tool -add_rpath /usr/local/hawq/lib/ /usr/local/hawq/./bin/gpcheckhdfs
  > ```

### 5.2 Apache HAWQ开发工具的使用

- 补充一下解释步骤说明

  - docker直接在本地装就好，不用在虚拟机内安装
  - 启动时的warning不需要管

- IDE配置，代码索引的使用

  > https://chiyang10000.github.io/notes/Eclipse-dafa-hao.html

- 测试运行

- HAWQ基本概念讲解

- 相关的DevOps流程

#### 5.2.1 待办清单

- [ ] 本地化编译安装是在是太困难了:)

  > 下面的内容依次进行，切换到docker内的命令会用另外一个方框标出。
  > 注意每个`exit`，该命令提醒你docker容器在后台运行。
  >
  > 1. Install and check docker available
  >
  >    ```bash
  >    docker run hello-world
  >
  >    # Hello from Docker!
  >    # This message shows that your installation appears to be working correctly.
  >    ```
  >
  > 2. Run and initialize container with image of CentOS in backend
  >
  >    **It takes around 10 min.**
  >
  >    ```bash
  >    docker rm -f hawq-dev
  >    docker run --detach --privileged=true --name hawq-dev centos:7 init
  >
  >    docker exec -it hawq-dev bash
  >    ```
  >
  >    ```bash
  >    # you are now login docker as root user
  >
  >    useradd -m gpadmin
  >    tee -a /etc/sudoers <<<'gpadmin ALL=(ALL) NOPASSWD: ALL'
  >    yum install -y xz gcc make wget git sudo which java openssh-server
  >
  >    systemctl restart sshd
  >
  >    exit
  >    ```
  >
  > 3. Repeat those documented in [Build and Install](https://cwiki.apache.org/confluence/display/HAWQ/Build+and+Install)
  >
  >    ```bash
  >    docker exec -it hawq-dev su - gpadmin
  >    ```
  >
  >    ```bash
  >    # you are now login docker as gpadmin
  >
  >    # 5 min
  >    git clone https://gitee.com/mirrors/hawq.git
  >    cd hawq
  >
  >    # 10 min
  >    sed 's|REPO=.*|REPO=http://yumazure.oushu-tech.com:12000/oushurepo/yumrepo/internal/linux/toolchain/|' -i .github/workflows/scripts/toolchain.sh
  >    source .github/workflows/scripts/toolchain.sh
  >
  >    sudo install -o $USER -d /usr/local/hawq
  >    ./configure
  >
  >    # 10 min
  >    make
  >    make install
  >
  >    exit
  >    ```
  >
  > 4. Install and start HDFS
  >
  >    ```bash
  >    docker exec -it hawq-dev su - gpadmin
  >    ```
  >
  >    ```bash
  >    cd hawq
  >
  >    # 5 min
  >    wget http://yumazure.oushu-tech.com:12000/oushurepo/yumrepo/internal/linux/toolchain/hadoop-3.3.0.tar.gz
  >
  >    sudo install -o $USER -d /usr/local/hadoop-3.3.0
  >    sudo ln -snf hadoop-3.3.0 /usr/local/hadoop
  >    sudo tee /usr/local/bin/hdfs <<<'exec /usr/local/hadoop/bin/hdfs $@'
  >    sudo chmod a+x /usr/local/bin/hdfs
  >    tar xf hadoop-3.3.0.tar.gz -C /usr/local/
  >
  >    case $(uname -s) in
  >      Darwin) .github/workflows/scripts/init_macos.sh ;;
  >      Linux)  .github/workflows/scripts/init_linux.sh ;;
  >    esac
  >    chmod 600 /home/gpadmin/.ssh/config
  >
  >    export HADOOP_HOME=/usr/local/hadoop
  >    tee -a $HADOOP_HOME/etc/hadoop/hadoop-env.sh << EOF_hadoop_env
  >    export JAVA_HOME=$(java -XshowSettings:properties -version 2>&1 | sed -nE 's|.*java.home = (.*)|\1|p')
  >    EOF_hadoop_env
  >    .github/workflows/scripts/init_hdfs.sh
  >
  >    exit
  >    ```
  >
  > 5. Initialize and start HAWQ
  >
  >    ```bash
  >    docker exec -it hawq-dev su - gpadmin
  >    ```
  >
  >    ```bash
  >    cd hawq
  >    
  >    source .github/workflows/scripts/toolchain.sh
  >    source /usr/local/hawq/greenplum_path.sh
  >    
  >    cp -af $HAWQ_TOOLCHAIN_PATH/dependency/package/lib/* /usr/local/hawq/lib/
  >    cp -af $HAWQ_TOOLCHAIN_PATH/gcc/lib64/* /usr/local/hawq/lib
  >    
  >    .github/workflows/scripts/init_hawq.sh
  >    
  >    exit
  >    ```
  >
  > 6. Use HAWQ
  >
  >    ```bash
  >    docker exec -it hawq-dev su - gpadmin
  >    ```
  >
  >    ```bash
  >    source /usr/local/hawq/greenplum_path.sh
  >    psql -d postgres
  >    ```
  >
  >    ```sql
  >    create table t as select generate_series(1, 5);
  >    select * from t;
  >    ```

- [ ] 留一个可选的作业，将上面的步骤整理成docker file，然后利用新的docker image在5min内启动hawq

- [ ] 停止容器并重启，然后重新启动HAWQ集群

  ```bash
  docker stop hawq-dev
  docker start hawq-dev
  docker exec -it hawq-dev su - gpadmin
  ```

  ```bash
  # restart HDFS
  hdfs --daemon start namenode
  hdfs --daemon start datanode
  hdfs dfsadmin -report
  
  # restart HAWQ
  cd hawq
  source .github/workflows/scripts/toolchain.sh
  source /usr/local/hawq/greenplum_path.sh
  
  hawq restart cluster -a
  
  exit
  ```

  然后试试上面的第6步。

### 5.3 项目任务布置

- Apache HAWQ概念知识巩固
- 提交流程和开发技巧

#### 5.3.1 待办清单

> 阅读网盘内`Apache HAWQ课件.pptx`的第四章（里面一共有四章，前面三章可以不管）。
>
> 同时配合搜索Apache HAWQ文档，回答以下问题。

- [ ] hdfs如何启动和停止？如何确定当前hdfs是否正常工作？如何确定hawq是否正常工作？

- [ ] hawq init大概干了什么？hawq init和hawq start有什么区别？修改hawq配置需要init还是restart？hawq重新安装之后时候是否需要init？

- [ ] hawq的master/segment日志放在那里？

- [ ] 如何在psql中查看某个查询的查询计划？

  <details><summary>点击展开答案</summary>


  ```sql
  EXPLAIN query;
  ```

  </details>

- [ ] master，segment，virtual segment，query dispater，query executor是什么？

- [ ] 如何获取query dispater，query executor的进程号？

- [ ] slice和gang什么关系？gang和query executor什么关系？

- [ ] query plan和virtural segment什么关系？virtual segment和query executor什么关系？

- [ ] QD是从master还是从segment fork产生？QE呢？

- [ ] QD的log打印在哪里？QE的log打印在哪里？

- [ ] 如何执行feature-test？如何执行某一个feature test case？

- [ ] 下图中，有几个session？哪个是master？哪个是segment？哪些是QD？哪些是QE？哪些是virtual segment？有GANG吗？

### 5.4 开发过程答疑

1. 根据实践情况进行调整
2. 根据实践情况进行调整
3. 中期开发实践检查和验收

   - 需要有有效的开发改动
4. 根据实践情况进行调整
5. 开发实践的初步点评和汇总交流

   - 开发内容的初步展示，需要形成初步的PR
6. 根据实践情况进行调整
7. 根据实践情况进行调整
8. 总结交流，点评各个任务

### 5.x 课程进度记录

#### 2021-03-11
课程中选择了HAWQ开发实践的同学在进入群聊后需要更改群昵称为真实姓名，便于统计选课同学的入群情况。

课程的后续安排我们将会在所有选课同学入群后开展。

#### 2021-03-12

大家好～

课程的共享材料位于
https://drive.weixin.qq.com/s?k=ANAABQcyAAovUZs0V5AMwA4wbDAO0

每周的实践内容更新在其中“偶数科技HAWQ开源开发实践.md”

这个md文件可以用typora或者文本编辑直接打开。



有半天内延时的网页版在 https://codechina.csdn.net/OSC/OSSD/-/blob/oushu-hawq/偶数科技HAWQ项目开源实践/偶数科技HAWQ开源开发实践介绍.md#5-课程计划

#### 2021-03-15

大家好～

第一次线上交流时间为03-16周二14：00~16：00或03-17周三16：00~18：00，通过腾讯会议进行。

请同学们自行选择自己合适的时间。线上交流前需完成两件事情

1. 安装好腾讯会议
2. 有可用的Linux/macOS环境。



课程的共享材料位于
https://drive.weixin.qq.com/s?k=ANAABQcyAAovUZs0V5AMwA4wbDAO0

每周的实践内容更新在其中“偶数科技HAWQ开源开发实践.md”

这个md文件可以用typora或者文本编辑直接打开。

#### 2021-03-16

大家好，根据昨天的交流情况我修订了一下课程计划和社区的部分文档，有空的同学可以先查看一下。

其中下载工具链和HDFS的那一步建议大家提前进行（更新了一下加速下载的方法）。

为了方便直接查看课程计划，公告里更新了一个网页版。

## 6. 评分标准

考核方式分为**硬性考核指标**和**企业导师主观评分**两部分，下面是初定的评分分数值比例。

- 硬性考核指标 **70%**

  - 合格 **30%**

    > 每个步骤递进**10%**。
    >
    > 1. 成功编译启动运行调试Apache HAWQ
    > 2. 对文档或者内核代码进行修改
    > 3. 形成一个有效的提交

  - 良好 **20%**

    > 独立完成一系列提交

  - 优秀 **10%**

    > 实现一个完整的功能

- 企业导师主观评分 **30%**

  > 由企业导师参考学校课程规定和同学表现进行调配。

## 7. 课程资源

- [HAWQ System Overview](http://hawq.apache.org/docs/userguide/2.3.0.0-incubating/overview/HAWQOverview.html)

- [更好的Hadoop数据仓库解决方案——HAWQ技术解析](https://blog.csdn.net/wzy0623/category_9268984.html])

  > HAWQ技术解析（一） —— HAWQ简介
  >
  > HAWQ技术解析（三） —— 基本架构

- https://cwiki.apache.org/confluence/display/HAWQ

- http://hawq.apache.org/docs/userguide/latest/index.html

- 数据库系统概念第6版

  > 基本概念参考

- 大数据浪潮之巅

  > 书的内容偏向新闻读物
  >
  > 可以根据书的目录去搜索相关的论文

- https://github.com/pingcap/awesome-database-learning