##source-list
[yum install guide](https://github.com/ju2wheels/yum-mirrorrepo)


#说一下source.list的格式
Ubuntu 软件仓库被分为四个部分:main（主要的）, restricted（受限的）, universe（广泛的） and multiverse（多元的），这主要根据我们对软件的支持能力，以及软件的目的是否符合我们的 自由软件哲学。 


标准的 Ubuntu 安装是所有能从 main（主要的）和 restricted（受限的）软件库中获得的软件的一个子集，你可以用诸如 Synaptic Package Manager 或者 Aptitude 之类的软件安装程序来安装额外的软件，其他的软件仓库可以通过修改 /etc/apt/sources.list 文件来添加，请查看 “man sources.list” 来获得更多关于编辑 sources.list 文件的信息。 

“main（主要的）”软件库 
Main 部分的软件仓库包含了自由软件，这些软件可以被自由地重新分发，并且被 Ubuntu 团队完全支持。这主要包括目前可以得到的最流行的和最可靠的开源程序，它们中的大多数会在安装 Ubuntu 时候默认被安装。 

在 main 软件库中的软件包括可以手动选择的程序，Ubuntu 开发人员、社区和用户都觉得这些程序重要，并且 Ubuntu 安全和发行团队乐意支持这些程序。当你从 main 软件库中安装软件时，你可以放心，这些软件都会得到安全升级和技术支持。 

我们相信，在 main 中的软件包括了所有大多数人需要的软件，来用于一个全功能的桌面环境或者只运行开源软件的网络服务器。 

Main 中软件程序的许可证都必须是自由的，但是 main 中也可以包含一些二进制固件和选定的字体，要修改它们必须获得作者的同意。在任何情况下，重新分发都是不受妨碍的。 

“restricted（受限的）”软件库 
我们保留了受限软件库是因为有些常用软件虽然没有一个完全的自由软件许可证，但是 Ubuntu 团队仍然支持它们。请注意，我们无法为这些软件提供完全支持，因为我们不可以自行修改它们，而只能向软件的真正作者提交问题报告。 

受限仓库中的有些软件会被安装在 Ubuntu CD 里，但是被很清楚地分隔开来以保证可以很轻松地删除它们。我们包括进了这些软件是因为，如果要让 Ubuntu 在某些机器上运行，它们是必需的。典型的例子是，一些显卡制造商发行的二进制驱动是 Ubuntu 在这些机器上运行的唯一方法。默认情况下，我们只使用开源软件，除非根本没有其他方法来安装 Ubuntu 了。Ubuntu 团队努力促使这些制造商加速这些软件的开源，以保证尽可能多的软件可以在自由软件许可证下使用。 

“universe（广泛的）”软件库 
Universe 软件库是自由、开源软件和 Linux 世界的一个快照。在 universe 中你几乎可以找到每一种开源软件，以及可以在各种不太开放的许可证下使用的软件，它们都是在各种开放代码的基础上自动建造的。来自 main 的基础工具链和系统库被用来开发这些软件并且通常是和它们同步维护，所以这些软件应该可以很好地和 main 中的软件一起安装和运行，但是它们得不到安全补丁和支持。Universe 软件库中包含了上千种软件，通过他们，用户可以在稳定的 Ubuntu 内核之上获得由广阔的开源世界提供的多样性和可制定性。 

Canonical 公司不保证为 universe 软件库中的软件提供定期的安全升级，但是社区会提供这些升级。用户需要知道使用 universe 中的软件包所固有的风险。 

流行的或者支持良好的软件将会从 universe 移动到 main 中，如果维护者愿意支持并使之符合 Ubuntu 团队为 main 制定的一系列标准。 

“multiverse（多元的）”软件库 
The “multiverse（多元的）”软件库 contains software that is "not free", which means the licensing requirements of this software do not meet the Ubuntu "main" Component Licence Policy. 

请您自行检查您使用这些软件的权利并遵守版权持有人所制定的许可证条款。 

这些软件不被支持并且通常不能被修改或升级，使用它们须自行承担风险。 

#Ubuntu不同版本库定义
每一行的开头是deb或者deb-src，分别表示直接通过.deb文件进行安装和通过源文件的方式进行安装。
deb或者deb src字段之后，是一段URL，之后是五个用空格隔开的字符串，分别对应相应的目录结构。

在浏览器中输入http://archive.ubuntu.com/ubuntu/，

并进入dists目录，可以发现有5个目录和前述sources.list文件中的第三列字段相对应。任选其中一个目录进入，可以看到和sources.list后四列相对应的目录结构。对于不同的版本使用的是不同的库，如下，根据不同版本，替换名称即可。

lucid（10.04）   

Natty(11.04)

Oneiric(11.10)

Precise(12.04)

Quantal(12.10)

Trusty(14.04)

Utopic（14.10）

Vivid（15.04）

Wily(15.10)



Xenial（16.04）

#举例Ubuntu 14.04的格式是Trusty
deb http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse

deb http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse

deb http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse

deb http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse

deb http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse

deb-src http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse

deb-src http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse

deb-src http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse

deb-src http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse

deb-src http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse

#更新步骤
    sudo cp /etc/apt/sources.list /etc/apt/sources.list_backup
    sudo gedit /etc/apt/sources.list
    sudo apt-get update
