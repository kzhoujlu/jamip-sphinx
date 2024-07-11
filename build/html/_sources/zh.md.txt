# JAMIP简介

**JAMIP** (Jilin Artificial-intelligence aided Materials-design Integrated Package) 是由吉林大学张立军课题组开发的人工智能辅助、数据驱动的材料设计集成软件包。软件包为满足材料基因工程与材料信息学的研究需求设计，涵盖半导体材料、介电材料、金属材料等材料体系，为基于功能材料大数据与人工智能机器学习算法结合的新材料发现和设计提供工具支撑。

课题组在发展的基于大规模高通量材料计算框架的材料设计方法基础之上，深度结合数据管理、分析及存储技术与机器学习数据挖掘算法，解决了系列材料信息学研究面临的关键技术难题，开发了拥有自主知识产权的材料设计集成软件包JAMIP。JAMIP软件包受中国版权局的保护，注册号是2017SR514752和2021SR0349238。软件包主体使用Python语言开发，代码开源，供国内外同行在签订版权协议的条件下免费使用。

软件包主体框架包含以高通量材料计算为核心的数据产生，数据收集、管理工具及数据存储，机器学习/数据挖掘功能模块。各部分之间高度融合，为高效产生、分析、管理和学习计算材料大数据，进而开展新材料设计与发现研究提供专业操作化软件平台。

i. 以高通量材料计算为核心的数据产生：

JAMIP具有强大的材料制造工坊，包含便于开展高通量材料计算的结构原型数据库（版权注册号2019SR1060756），仍在不断发展中的结构操作方法集（可方便快捷构建缺陷、表面、晶界、异质结等复杂材料结构），为批量产生用于大规模高通量材料计算的材料结构提供了工具基础。JAMIP集成的高通量第一性原理计算引擎（支持VASP、Quantum Espresso等计算软件）可针对批量生成的材料结构进行高度自动化的计算模拟。软件集成的自动化任务递交、监控、纠错模块为计算任务的高效、顺利完成提供保障。以下列出当前JAMIP版本支持的材料性质计算流程模块（以VASP程序为例）：

*   自洽场计算与结构优化；
*   热力学性质：分解焓，Convex hull，Triangle zone；
*   电子结构：能带结构，电子态密度，总及部分电荷密度，成键轨道分析、形变势、电荷布居分析等；
*   力学性质：弹性模量，体模量，形变势，泊松比等；
*   光学性质：光吸收谱计算，介电函数，激子结合能，太阳能电池理论转换效率、非线性二次谐波成像等；
*   声子与热学性质：声子谱及声子态密度，软模相变，gruneisen常数、热导率等；
*   电输运性质：载流子有效质量，载流子迁移率；
*   其他性质：XRD图谱，径向分布函数，容差因子及八面体因子(钙钛矿结构)

我们正致力于不断扩展以上材料性质计算流程模块，涵盖更多功能材料体系的性质，为实现功能导向的材料设计提供有效计算工具支撑。

ii. 数据收集、管理工具及数据存储：

JAMIP集成了针对不同类别的功能材料，对高通量第一性原理计算结果的自动化数据提取、分析工具。针对材料信息学的材料大数据特点，集成了以Django框架为基础的数据库平台接口，支持MySQL，Sqlite3，postgresql等多种主流数据库管理语言。数据库系统实现使用环境的纯Python化，用户无需学习复杂的结构化查询语言（SQL），即可在多种平台上对特定研究课题的计算数据进行存储，共享与快速检索。目前数据收集、管理工具及数据存储模块支持以下功能：

*   高通量计算数据自动提取；
*   计算数据分析工具、绘图工具；
*   计算数据的自动存储到数据库；
*   数据库的便捷数据查询与导出

iii. 机器学习/数据挖掘模块：

在JAMIP当前版本中，我们集成了数据前处理，数据特征工程，以及常用机器学习算法的模型构建和性能评估子模块。用户可根据训练和测试数据集的特征，选择合适的机器学习算法开展机器学习研究，探索材料性质与结构之间的内在关系、不同性质之间的关联、主导材料高性能化的物理规律，进而开展新材料设计。
目前机器学习/数据挖掘模块支持以下功能：

*   数据预处理：数据清洗、类别特征编码；
*   特征工程：特征缩放、特征构造、特征选择；
*   机器学习模型构建及后处理、模型评估；
*   基于数据挖掘结果开展材料设计研究

如果想了解更多的关于JAMIP方法和程序，请参考以下文献:
++Xin-Gang Zhao, Kun Zhou, Bangyu Xing, Ruoting Zhao, et al., Yuhao Fu, Lijun Zhang, “JAMIP: an artificial-intelligence aided data-driven infrastructure for computational materials informatics”, arXiv:2103.07957 (2021)++

    (1) JAMIP: An Artificial-Intelligence Aided Data-Driven Infrastructure for Computational Materials Informatics. 
    Science Bulletin 2021, 66 (19), 1973–1985. https://doi.org/10.1016/j.scib.2021.06.011.

虽然JAMIP开发团队和现有用户已对JAMIP软件包进行了大量测试，但由于新功能的不断添加和算法的不断完善，程序中的bug在所难免。当您在使用过程中发现任何问题，请随时和我们联系，我们将非常高兴地接受所有用户提出的宝贵建议和批评。
如果发现程序中的bug，请通过电子邮件发送输入和输出文件的副本到JAMIP开发团队(<admin@jamip-code.com>)，感谢大家的理解与支持。

# 1. 软件安装及运行环境配置

当前JAMIP版本基于Linux环境开发、安装和运行，安装及运行环境配置步骤如下：

## 1.1 软件安装

#### 1.1.1 下载源代码并安装

在JAMIP软件主页<http://www.jamip-code.com）注册并签订版权协议，下载源码安装包[JAMIP-V1.1.tar.gz](http://jamip-code.com/download.html)
解压后执行：

    sh install.sh

JAMIP依赖的Python库将在用户机器联网状态下自动安装。使用Anaconda3等Python发行版可预先解决软件所需的大部分依赖。
以下是依赖的Python库：

*   [Python](https://www.python.org/) ≥ 3.7
*   [numpy](https://numpy.org/) ≥ 1.14
*   [matplotlib](https://matplotlib.org/) ≥ 2.1
*   [scipy](https://scipy.org/) ≥ 1.5.4
*   [scikit-learn](https://scikit-learn.org) ≥ 0.22
*   [Django](https://www.djangoproject.com/) = 3.1
*   [ruamel.yaml](https://yaml.readthedocs.io/en/latest/) ≥ 0.16
*   [spglib](http://spglib.github.io/spglib/)
*   [psutil](psutil.readthedocs.io/)
*   [jinja2](https://jinja.pocoo.org)

如果用户需要离线安装JAMIP，可按以下步骤安装：

    1. 在有网络连接的机器上下载Anaconda3
    2. 执行解压安装命令后，使用pip命令打包全部依赖库
    sh install.sh
    pip download -d package -r jamip.egg-info/requires.txt
    3. 将Anaconda3安装包，jamip安装包和上一步生成的依赖库上传至离线机器，解压后执行安装命令
    pip install --no-index --find-links=package -r jamip.egg-info/requires.txt
    sh install.sh

#### 1.1.2 环境变量初始化

在执行安装脚本时，程序将自动完成对基本环境的配置。
JAMIP需要在用户的家目录创建 `.jamip`文件夹，其中可执行程序的路径为：`$HOME/.jamip/bin`，安装时将自动在`~/.bashrc`内添加环境变量。

#### 1.1.3 程序安装测试

在终端输入jp指令正常执行：

    jp -h/--help

## 1.2 程序运行环境配置

初始安装JAMIP程序时，需要对高通量计算环境（集群参数、第一性原理计算的默认参数）和数据库做初始化的环境配置。所有配置文件都在`$HOME/.jamip/env`路径下。
在程序运行过程中，将基于上述目录下的默认配置文件，在计算目录下生成配置文件副本。建议用户在软件安装后首先查看及修改配置文件，避免因参数设置问题导致的程序运行错误。

#### 1.2.1 集群参数

在执行计算时，JAMIP默认会基于初始化的集群参数（任务管理系统信息、机器硬件信息）生成作业提交文件，实现跨集群的任务提交与管理。

JAMIP目前预置了三种作业管理系统的配置文件：PBS、LSF、SLURM，分别对应在 `$HOME/.jamip/env` 目录下的`pbs.yaml`, `lsf.yaml`，`slurm.yaml`。我们正在持续扩展对其他作业管理系统的支持。作业管理系统配置文件的格式如下（以PBS作业管理系统为例）：
**pbs.yaml**

    job_name: VASP.pbs   # 默认的提交任务名称
    manager: PBS         # 作业管理系统类型
    queue: batch         # 默认的提交队列名
    nodes: 1             # 使用的计算节点数
    cores: 36            # 单个计算节点使用的核数
    walltime: 12:00:00   # 任务最大运行时间
    cmd: qsub            # 提交任务的命令
    mpi: mpirun          # 并行任务的命令
    maximum: 10          # 提交队列中，默认的提交任务上限值（排队和计算中的任务）
    env:                 # 自定义程序执行所需的依赖库/编译器
    -  module load intel # 例如：加载intel编译器
    -  export PATH=~/anaconda3/bin:$PATH # 例如：添加Python环境变量

上述集群参数将传递到Jinja2模板中，生成作业提交文件。提交模板如下：

**pbs.template**

    #!/bin/bash
    #PBS -N {{ job_name }}
    #PBS -q {{ queue }}
    #PBS -l nodes={{ nodes }}:ppn={{ cores }}
    #PBS -l walltime={{ walltime }}
    #PBS -o {{ output }}
    #PBS -e .error

    cd $PBS_O_WORKDIR

    {% for line in env %}  # for循环输出环境变量
    {{ line }}
    {% endfor %}

    python3 {{ script }} {{ root }} {{ outdir }} {{ pool }} > .running
    # 可执行python文件 + 作业提交目录 + 作业计算目录 + 任务池

最终生成的作业提交脚本如下：
**submit.sh**

    #!/bin/bash               # shell路径
    #PBS -N VASP.pbs          # 任务名
    #PBS -q batch             # 队列名
    #PBS -l nodes=1:ppn=36    # 节点数：核数
    #PBS -l walltime=12:00:00 # 程序最大运行时间
    #PBS -o .output           # 作业标准日志输出到 .output
    #PBS -e .error            # 作业异常信息输出到 .error
     
    cd $PBS_O_WORKDIR         # 切换目录到提交目录 

    module load intel         # 加载程序执行所需的依赖库/编译器
    export PATH=$HOME/anaconda3/bin:$PATH
     
    python $JAMIP_PYTHONPATH/manager.py $SUBMIT_dir $JOB_dir NAME.dat  > .running

**备注：**
在执行`jp -r prepare`命令后，如果当前目录下不存在集群配置文件`.cluster`，JAMIP将根据默认路径下（`$HOME/.jamip/env`）的集群配置文件生成文件副本。确认配置文件生成后，JAMIP将测试作业提交模板所需的参数是否完整提供，若存在缺少参数将通过屏幕日志的方式进行提醒。
在后续任务提交和程序运行期间，JAMIP将从该配置文件加载所需的集群参数。
JAMIP允许用户自由修改提交模板和配置文件，以支持在任意作业管理系统上提交任务和扩展功能。如果您想了解更多作业管理系统的配置方法和管理模块，请参阅集群管理模块。

#### 1.2.2 高通量计算默认参数

当用户使用DFT程序计算一组材料的性质时，通常会基于固定的流程和计算参数。\
JAMIP为常用的计算任务提供了一套稳健的计算流程，默认的任务计算参数储存在`$HOME/.jamip/env`目录下，如`vasp.yaml`（用于VASP）、`qe.yaml`（用于QE）。用户可以根据实际计算需求，修改特定任务的初始化参数。以VASP的计算任务为例：

**vasp.yaml**

    base:
       system: jamip
       ismear: 0
       sigma: 0.05
       algo: fast
       npar: 4
    relax:
       addgrid: true
       nelm: 5
    scf:
       lcharg: true
       lwave: true
    dos:   
       lwave: false
       ismear: -5
       nedos: 3001
       lorbit: 11

JAMIP目前支持的第一性原理计算软件有：VASP和 Quantum Espresso。我们正在更新对其他主流计算软件和程序的支持。
**备注：**
在执行 `jp -r prepare`命令来生成计算的任务池后，JAMIP将在当前目录下生成/更新任务计算参数的文件副本`.incar`。在程序运行期间，JAMIP将从该副本文件中加载计算参数。用户可以通过修改此文件，实现动态地修改本次计算参数。
在修改`.incar`文件时，尽量简化参数设置，避免因重复设置参数而导致的计算参数遗忘或更新混乱 (详细信息见 [DFT参数设置](#dft参数))

**下面列出了计算参数文件中通用的key值：**

    base：        默认参数集，各任务的incar均在此基础上更新
      
    计算任务部分：
    relax:        结构优化参数
    scf:          自洽计算参数
    band:         能带计算参数
    dos:          态密度计算参数
    force:        力常数计算参数
    optics:       含频介电常数参数
    hse_gap:      hse修正带隙计算
      
    交换关联泛函部分：
    soc:          自旋轨道耦合计算参数
    hse:          杂化泛函参数
    gw:           gw参数
    ldau:         lda+U参数

#### 1.2.3 数据库参数

JAMIP中的数据库是以Django框架为基础开发的，数据库系统实现了使用环境的纯Python化，用户无需学习复杂数据库编程方法和结构化查询语言（SQL），通过调用JAMIP程序内部方法，就能完成对数据库中数据的更新维护及查询操作。JAMIP数据库支持多种主流关系型数据库后端，如 MySQL，MariaDB，Sqlite3，Oracle，PostgreSQL。

在使用数据库相关功能前，用户需要先完成数据库初始化和Django的参数配置工作。\
目前，JAMIP支持自动配置MySQL和Sqlite3数据库，数据库配置文件保存在 `~/.jamip/env/django.json`\
如果您是轻量级用户，推荐您使用Python环境自带的Sqlite3数据库。下面列出初始化数据库的相关命令：

    jp --django mysql           # 配置MySQL参数，交互式输入数据库名称、登陆等信息
    jp --django sqlite          # 配置Sqlite3参数，默认数据库生成路径为代码包的db目录下
    jp --django makemigrations  # 数据库迁移--生成迁移文件
    jp --django migrate         # 数据库迁移--同步到数据库

# 2. 快速使用指南

JAMIP的核心命令行工具为：`jp`。用户可以通过该命令，与JAMIP进行交互 (完整的jp命令介绍请参阅：jp命令介绍)

本章以单晶硅(空间群号：227)的VASP能带计算为例，展示如何使用jp命令进行如下操作：文件准备、参数配置、任务提交、任务检查、以及数据处理等一般计算流程。

## 2.1 高通量计算任务输入文件准备

首先，用户需要先完成以下准备工作：

1.  准备VASP可执行程序，确认运行所需的环境变量
2.  准备完整的VASP赝势库，用于JAMIP程序自动生成赝势
3.  待计算的结构文件(以单晶硅为例)，输入文件的格式可以是vasp、cif、qe等

#### 2.1.1 任务控制文件

JAMIP通过Python文件(`input.py`)设置计算任务的主要参数。程序将根据`input.py`内的设置的参数生成计算类。可通过`jp -i vasp` 命令生成`input.py`文件，示例如下(更为详细的信息请参阅：[input参数设置]())：

```python
from jamip.abtools.vasp.setvasp import SetVasp
from jamip.compute.prepare import Prepare
 
def jamip_input(name=None,*args,**kwargs):
     vasp=SetVasp()                            # 初始化SetVasp类
     vasp.program = '/install_path/vasp_std'   # vasp程序路径
     vasp.potential = '/install_path/paw_pbe'  # vasp赝势目录
     vasp.tasks = 'relax scf band'             # vasp计算任务列表
     
     vasp.xc_func = 'pbe'      # vasp计算使用的参数集
     vasp.force = 1e-2         # vasp计算的力收敛标准，对应EDIFFG = -1e-2
     vasp.energy = 1e-6        # vasp计算的能量收敛标准，对应EDIFF = 1e-6
     vasp.cutoff = 1.3         # vasp计算的截断能，支持两种设置方式：1)直接设置截断能值，如：520
                               # 2) POTCAR中全部ENMAX中最大值的倍数，如：1.3 (即：ENCUT=1.3*ENMAX)
     vasp.kpoints = 0.25       # vasp计算使用的K点类型，0.25表示采用：KSPACING = 0.25
     
     pool=Prepare.pool(vasp)   # 初始化Prepare类
     pool.set_structure('input','output') # 设置计算的输入和输出目录
     pool.set_extra()          # 生成.extra文件，可选功能
     # 在此示例中，input为输入结构文件目录， output为计算输出目录
     pool.save('Silicon.dat')  # 保存任务池，任务池名为'Silicon.dat'
     Prepare.cluster('pbs')    # 生成/更新.cluster文件，可选(pbs/lsf/slurm)
     Prepare.incar(vasp)       # 生成/更新.incar文件，根据计算任务添加参数字典
     Prepare.links(vasp)       # 生成.link文件，初始化计算任务间的依赖关系
```

**备注：**
进行批量计算时，需要将结构文件保存在同一目录下。在生成任务池时，JAMIP程序将从该目录统一读取结构。以上面的文件为例，用户需要将所有结构文件保存到`input`文件夹内。
用户需要为结构文件设置正确的后缀，目录内出现无法识别的文件将导致结构读入失败。
结构文件名将用于后续的计算目录、批量绘图等的命名。

#### 2.1.2 本地配置文件

JAMIP采用在任务提交目录下生成配置文件副本的方式，方便用户在计算时根据任务类型自由设置使用的计算参数和计算资源。
在正式任务提交前，建议用户对下列配置文件进行检查：

*   `.incar` 用于设置批量VASP计算的INCAR控制参数（以VASP计算为例）；
*   `.cluster` 用于设置批量计算使用的集群参数；
*   `.extra` 用于设置针对特定结构的参数，如计算磁性结构、铁电极化、激发态等；
*   `.link` 用于设置计算任务间的依赖关系
    **备注：**

1.  当前目录不存在配置文件时，执行`jp -r prepare`后，JAMIP将基于`$HOME/.jamip/env`下的默认模板生成配置文件；
    如果已经存在本地配置文件，执行`jp -r prepare`，JAMIP将对现有配置文件进行检查并更新。
2.  `.extra`文件仅在特定计算任务中生效，详细信息见：补充参数设置

在完成准备工作后，提交目录下应当包含如下文件：

    |-- input.py # 任务控制文件
    |-- .incar   # 计算参数配置文件
    |-- .cluster # 集群参数配置文件
    |-- .extra   # 补充参数配置文件
    `-- Input    # 结构文件目录
       |-- Si.vasp # 结构文件
       `-- ...

## 2.2 高通量计算任务提交

JAMIP通过任务池文件实现对任务的管理和批量自动化提交，以下是提交使用的命令

    jp -r prepare        # 根据input.py，在当前目录下生成任务池
    jp -r qsub -f Silicon.dat # 提交任务池<Silicon.dat>中的任务

**备注：**

1.  执行任务提交命令后，JAMIP将向作业管理系统提交若干任务，单次提交的任务数由`.cluster`内的`maximum`参数决定(默认为10)
2.  JAMIP程序将在上一任务完成后，自动从任务池中提交新的任务，维持计算队列中的任务总数不变
3.  任务提交后，后续程序的运行依赖于任务池文件和同目录下的配置文件，请不要在计算完成前删除或修改任务池。

提交任务后的目录结构：

    |-- input.py         # 任务提交脚本
    |-- input            # 结构文件目录
    |  `-- Si.vasp       # 结构文件
    |-- Silicon.dat      # 任务池
    |-- .cluster         # 集群配置文件
    |-- .incar           # INCAR配置文件
    |-- .link            # 任务依赖配置文件
    `-- output           # 计算总目录
       `-- Si.vasp       # 计算目录
          |-- relax      # 结构优化计算目录
          |  |-- S0      # 分步优化，S0为粗优化
          |  `-- S1      # 分布优化，S1为第一步标准优化
          |-- scf        # 自洽计算目录
          `-- electric   # 电子结构目录
              `-- band   # 能带计算目录

## 2.3 任务状态监控与检查

JAMIP提供了多种输出日志，用户可以从日志中获取任务的详细信息。以下日志文件都存储在计算任务的根目录中：

*   **实时输出：**
    `.status` 记录任务的完成状态
    `jamip.log` 累积记录当前目录的任务运行信息
*   **计算完成后由作业管理系统输出：**
    `.output` 作业标准输出信息
    `.error`  作业标准报错信息

用户可以使用`jp`命令查询任务池中所有任务的计算状态统计：

    $ jp -c show -f Silicon.dat # show命令查看当前任务池的完成状态
    +--------+-------+--------+-------+-------+----------------+
    | job_id | prior | status |  scf  | relax |      path      |
    +--------+-------+--------+-------+-------+----------------+
    | 203764 |   9   |    C   | True  |  True | OUTPUT/Si.vasp |
    +--------+-------+--------+-------+-------+----------------+

    # 表格信息说明 ：
    > job_id : 在作业管理系统中的任务号; 
    > prior : 任务优先级（依赖于自重启计算次数，自重启计算次数越多优先级越低）; 
    > status : 任务运行状态; W 代表任务未提交；R 代表任务已提交，尚未结束；C 代表任务正常结束；
    > relax/scf ：各个子任务的完成状态; 
    > path ：任务计算路径（基于提交目录的相对路径）

**备注：**
查询表格中的`status`仅表示JAMIP对任务完成信息的记录，实际运行情况以作业管理系统的查询结果为准。
如果一个任务持续保持R状态，说明其在运行过程中意外退出，用户可以进入该任务的计算目录，从`.error`文件中获取该任务报错信息。

**任务状态文件 .status ：**

    relax/S1:          # 任务计算路径，状态字典的主键
     task: relax       # task: 任务名称
     finish: true      # finish：计算是否完成(vasp程序正常结束)
     success: true     # success: 任务是否完成(收敛或正确输出文件)
     electronic: true  # electronic：电子步收敛
     force: 0.0057     # force：晶格力收敛
     ionic: true       # ionic：离子步收敛
    scf:
     task: scf         # scf任务状态
     finish: true 
     success: true
     electronic: true
    electric/band:
     task: band        # band任务状态
     finish: true
     success: true

## 2.4 数据提取与处理

#### 2.4.1 数据提取与存储

JAMIP的数据处理主要依靠内部的Python提取模块实现，运行`jp`命令可以在终端内实现部分功能，用户也可以基于相关模块手动构建数据提取脚本。详细信息请参阅：`jamip.analysis`代码说明文档。

**使用`jp -o`命令可以在命令行环境快速查看数据，例如：**

    $ jp -o bandgap free_energy emass # 提取并输出统计数据
    +---------+---------+----------+-------------+--------+--------+
    |   path  | bandgap | isdirect | free_energy | H-mass | e-mass |
    +---------+---------+----------+-------------+--------+--------+
    | Si.vasp |  0.7041 |  False   | -43.380448  | 1.013  | 0.287  |
    +---------+---------+----------+-------------+--------+--------+
     
    $ jp -o csv bandgap free_energy emass # 提取并以csv格式输出数据
    ---------------------- 文件分割线 -------------------------
    format,bandgap,isdirect,free_energy,H-mass,e-mass
    Si.vasp,0.7041,False,-43.38044857,1.013,0.287

使用功能化函数提取数据，例如提取vasp计算的能带数据

    # 提取vasp计算的能带数据
    from jamip.analysis.vasp import BandFinder
    path = '/home/jamip-test/ICSD/CsPbI3.vasp' # 计算目录
    bf = BandFinder(path).get_data()           # 实例化类
    banddata = bf.bands                        # 获取能带数据
    kpoints = bf.kpoints                       # 获取K点坐标数据

#### 2.4.2 利用数据绘图

JAMIP以Python脚本的形式提供常用的绘图功能，用户可以使用绘图脚本为一组计算批量绘图。
执行`jp -i plot`命令生成绘图脚本，代码如下：

    from jamip.utils.plot import globalvar as gl

    gl.band.emin = -1
    gl.band.emax = 3
    gl.band.xlabel = ''
    gl.band.ylabel = 'Energy (eV)'

    if __name__ == '__main__':
        from jamip.utils.plot import Plot
        pl = Plot(path='./')  # 设置绘图使用的路径
        
        # 设置需要绘制的图像(组合图)
        pl.plots('fatband')   
        
        # 设置需要绘制的图像、路径和参数(单图)，以下两种方法等价
        pl.plot('dos', path='./')    #
        pl.plot_band(path='./',fname='band.png') 

代码包含全局变量设置和绘图功能调用两部分，通过设置全局变量，用户可以调整绘图区间、标题内容等参数。
为方便用户修改，JAMIP令相同类型的绘图任务使用同一组全局变量，任务类型如下：

| 类型     | 绘图功能                                                 |
| ------ | ---------------------------------------------------- |
| band   | band, fatband, hseband, unfolding, phband, gruneisen |
| dos    | dos, spdos, cohp, phdos                              |
| absorb | absorb, dielectric, shg                              |
| base   | converge, softmode, tdm                              |

**可设置的变量：**

| 变量名     | 变量类型  | 介绍      |
| ------- | ----- | ------- |
| emax    | float | 能量区间最大值 |
| emin    | float | 能量区间最小值 |
| limit   | float | 态密度区间上限 |
| scissor | float | 剪刀算符    |
| title   | str   | 图像标题    |
| xlabel  | str   | 图像x轴标签  |
| ylabel  | str   | 图像y轴标签  |

**支持的绘图功能：**

    电子结构相关：
    band: 能带
    fatband: 投影能带 
    dos: 态密度
    absorb： 光吸收谱
    dielectric: 介电函数
    unfolding: 能带反折叠
    hseband： 杂化泛函能带
    tdm: 跃迁矩阵元
    cohp: 成键轨道分析
     
    phonopy相关：
    phband: 声子谱
    phdos: 声子态密度
    gruneisen: Gruneisen常数
    thermal: 热膨胀系数
    softmode: 软膜相变
     
    光谱相关：
    xrd: x射线衍射
    ir_spectrum: 红外光谱
    raman_spectrum: 拉曼光谱
     
    其他：
    convex_hull: 二元相图分析
    triangle_zone: 三元相图分析

对于其他绘图属性的设置，例如画布尺寸、字体大小、线宽等，JAMIP基于Matplotlib包的样式表实现，相关配置文件存储在：`$HOME/.jamip/viewer/`。

与上面全局变量的调用方式类似，用户可通过修改目录下绘图功能对应的配置文件`xxx.mplstyle`，进行绘图参数的调整。详细的文件配置方法可参考[matplotlib官网](https://matplotlib.org/stable/tutorials/introductory/customizing.html)。

**基础绘图样式表：** `$HOME/.jamip/viewer/base.mplstye`

    figure.dpi: 72
    figure.figsize: 10,7
    font.size: 18
    axes.titlesize: 25
    axes.labelsize: 24
    lines.linewidth: 2.5
    lines.markersize: 16
    xtick.labelsize: 20
    ytick.labelsize: 20

默认绘图样式（字体大小、线宽等）适用于长轴为10-14的画布，用户通常需要成比例的修改画布和内容大小。
在查找样式表文件时，JAMIP将按`job -> basejob -> base`的顺序查询可用的样式表，例如`hseband`任务将依次查询 `hseband.mplstyle`,`band.mplstyle`,`base.mplstyle`，用户可根据自身绘图习惯新建并修改样式表。

**备注：**
JAMIP支持用户绘制组合图，并根据绘图类型自动调整画布大小。以`band+dos+tdm`图为例：

    pl = Plot(path='output/Si.vasp')
    pl.plots('band','dos','tdm')

组合图默认保存为`banddostdm.png`，如下图所示：
![png](https://note.youdao.com/yws/api/personal/file/WEB587e23db24eb298b5a1e8537c1d7a45a?method=download\&shareKey=c0fbed5acea41ebafd7edf225382c3f4)

#### 2.4.3 数据挖掘研究

在利用高通量软件进行大规模材料计算的同时，如何充分利用计算过程产生的大量数据，从中挖掘出有价值的规律性认知，是材料信息学的研究的重点。
JAMIP数据库和机器学习包为材料计算的大数据分析提供了有力的工具，用户可以将海量的计算数据转化为机器学习可用的描述符集，并在需要时从数据库中提取并加以分析。下面介绍构建描述符集的基本方法。

    import os
    from jamip.db.connect import Read,Structure
    from jamip.ml.descriptorsSet.descriptorsSet import DescriptorsSetBuilder
     
    structures = []
    for file in os.listdir('TEST'):
     raw = Read(os.path.join('TEST',file)).run()
     s = Structure().create(raw, isPersist=False)
     structures.append(s)
    features = ['mass','natoms','volume','a','b','c','BX'] # 设置提取特征
     
    df=DescriptorsSetBuilder(structures).set_features(features) # 提取特征
    df.save('test.csv') # 将提取结果存入csv文件

#### 3.4.2 StructureFactory类

结构工厂类中集成了大量常用的结构操作方法，通过对这些操作方法的进一步组合，可以实现复杂结构的构建。此外，这些方法中大部分都支持链式操作。以下对类中的方法进行简单介绍：

**注意：** 结构操作方法返回值均为类自身，需要调用其类属性structure获取结构操作后的结构对象。

**建议：** 在结构操作过程中，设置isUpdatedInfo和isPersist为False，可以提高程序的响应速度，并且可以避免将操作过程中产生的无用结构保存进数据库；在完成所有结构操作后，调用操作后得到的结构对象的update()方法，同步内存中内建数据结构中的数据，可以避免后续抛出一些异常情况。

**参数格式：** 结构操作方法的特定输入变量需要满足一定格式，在此进行约定：

*   **原子的标准格式化数组**，其格式为：\[元素名，坐标，坐标类型]，例如：
        ['Na', 0.1, 0.0, 0.0, 'Direct'] 
        ['Na', 5.234, 0.0, 0.0, 'Cartesian']
        ['Na', 0.1, 0.0, 0.0] (当坐标类型缺省时，默认坐标类型为分数坐标)
        其中元素名可用物种信息替代，例如：
        ['Na1+', 0.1, 0.0, 0.0, 'Direct']
        ['Na1+', 5.234, 0.0, 0.0, 'Cartesian']
*   **原子坐标或参考点坐标**，其格式为：\[坐标，坐标类型]，例如：
        [0.1, 0.0, 0.0, 'direct']
        [5.234, 0.0, 0.0, 'Cartesian']
        [0.1, 0.0, 0.0] (当坐标类型缺省时，默认坐标类型为分数坐标)
*   **方向向量或旋转轴向量**，其格式为\[向量，向量类型]，例如：
        [1, 0, 0, 'direct']
        [2.6, 2.6, 0, 'Cartesian']
        [1, 0, 0] (当坐标类型缺省时，默认坐标类型为分数坐标)
*   **旋转角**，其格式为\[角度，角度类型]，例如：
        [30, 'Degree']
        [0.2, 'Radian']

***structure***
类属性，获取结构类的当前结构对象

***raw\_structure***
类属性，获取结构类的初始结构对象

***zoom(scale, isPersist=False)***
晶格基矢缩放。

*   `scale: float` 放缩系数值
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中

***scale(direction, isPersist=False)***
对指定晶格基矢方向，进行晶胞的放缩。

*   `direction: list` 指定需要缩放的晶格基矢方向的系数
    其数据格式为：\[ *scale of a, scale of b, scale of c* ]，如：
        [0.9, 1, 1] (只压缩a方向0.9)
        [0.9, 0.9, 1] (压缩a和b方向0.9)
        [0.9, 0.9, 0.9] (三个方向都压缩0.9，等同于调用zoom(0.9))

*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中

***add\_atoms(atoms, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
在结构中增添多个原子。

*   `atoms: array-like` 包含原子信息的列表数组，数组的每个原子可以为以下形式：
    a. 原子的实例化对象，如：\[ *atom0, atom1, atom2* ];
    b. 原子的标准格式化数组，如：\[\[元素名，坐标，坐标类型], ... ]
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `isNormalizingCoordinate: bool, default: True`是否规范化原子的坐标，移除周期性，
    保证原子位于晶胞基矢表示的晶胞内部，如：分数坐标1.3将转化为0.3
*   `precision: float, default: 1e-3`检查过程中判定原子是否重叠的精度参数，单位为埃（Å）
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***del\_atoms(atoms, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
在结构中删除多个原子。

*   `atoms: array-like` 包含原子信息的列表数组，数组的每个原子可以为以下形式：
    a. 原子的实例化对象，如：\[ *atom0, atom1, atom2* ];
    b. 原子的标准格式化数组，如：\[\[元素名，坐标，坐标类型], ... ]
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***substitute\_atoms(atoms, symbol\_of\_elements, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
替换结构中的多个原子的元素类型。

*   `atoms: array-like` 包含原子信息的列表数组，数组的每个原子可以为以下形式：
    a. 原子的实例化对象，如：\[ *atom0, atom1, atom2* ];
    b. 原子的标准格式化数组，如：\[\[元素名，坐标，坐标类型], ... ]
*   `symbol_of_elements: string or list` 替换成的新元素名。如果全部需要替换的原子都换成同一种元素，可以仅指定一个元素类型。如：'Na'。否则，需要给出每个原子对应的新的元素名的列表数组，如：\[ *'Na', 'Na', 'Na'* ]。
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***center(direction, dtype\_of\_move='position', isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
按照给定的方向，移动结构中的原子，实现中心对齐。

*   `direction` 原子移动的方向向量，格式为：\[ *a, b, c* ]，
    如：`[1,0,0]` (沿a方向)、`[0,1,0]`(沿b方向)、`[0,0,1]`(沿c方向)
*   `type_of_move: {'position','mass'}, default: 'position'` 指定对齐方式。
    其中，'mass'为按质心对齐，'position'为以左右边界位置对齐
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***vacuum(direction, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
在指定方向增加真空层。

*   `direction: list`为沿着某个晶格矢量方向增加真空层的方向向量
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `isCenter: bool, default: True` 是否中心对齐结构
*   `distance: float, optional` 将结构中的所以原子沿着给定的方向移动指定的距离，单位为埃(Å)。
    注意：移动距离不能超过添加真空层之后的晶胞参数的长度，即不能将原子移动到晶胞之外
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***redefine(operator\_matrix, isPersist=False)***
利用给出的操作矩阵M，重新定义晶格，其转换关系为：`C'=C x M`。

*   `operator_matrix: int array-like of shape (3, 3)` 3x3的整数矩阵(M)，例如：`[[0,1,1], [1,0,1], [1,1,0]]`
    注意：晶胞体积要大于0，即M的行列式绝对值为正整数。
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中

***surface(hkl, maxindex=None, saxis='c', isPersist=False, \*\*kwargs)***
生成指定晶面的结构。

*   `hkl: array-like` 晶面的Miller指数，格式为\[h, k, l]，如\[1, 1, 0] （均为整数）
*   `maxindex: int` 搜索的晶格矢量的范围，默认值为hkl的最大值。低对称性结构在搜索正交晶矢时可能失败，需要用户手动修改maxindex。
*   `saixs: str, defaule: 'c'` 生成晶面在结构中对应的晶轴
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中

***standardize(isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
将当前结构转化为标准化结构。

*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度
*   `hall_number: int, default: 0` 霍尔符号。注意，如果该值为0，默认选取Seto网站列出的所有可选空间群列表中的最小序数对应的空间群结构。

***primitive(symprec=default\_constants.symprec.value, isPersist=False)***
获取原胞结构。

*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中

***conventional(symprec=default\_constants.symprec.value, isPersist=False)***
获取单胞结构。

*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中

***supercell(dim, isPersist=False, \*\*kwargs)***
获取超胞结构。

*   `dim: list` 需要扩胞的大小，格式为\[ *a, b, c* ]，如：\[2, 2, 2]
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***joint(jointed\_structure, direction, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
在给定的方向上，拼接两个晶体结构。注意：拼接时，传入的jointed\_structure结构，会对垂直拼接方向的横截面进行缩放，以使两个结构的横截面匹配。

*   `jointed_structure`拼接结构实例化对象。
*   `direction: list` 指定拼接的方向向量，格式为\[方向向量，方向向量类型] (注意：只能为'Direct')，例如：
          [ 1, 0, 0, 'Direct'] (拼接到a轴右侧)
          [-1, 0, 0, 'Direct'] (拼接到a轴左侧)
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***rotation(atoms, axis, theta, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
对选定的原子进行旋转操作。注意，如果不设置旋转的原点位置，默认的原点设置为坐标系的原点\[0, 0, 0]。

*   `atoms: array-like` 需要旋转的原子的列表数组，数组的每个原子可以为以下形式：
    a. 原子的实例化对象，如：\[ *atom0, atom1, atom2* ];
    b. 原子的标准格式化数组，其格式为：\[元素名，坐标，坐标类型];
*   `axis: list` 旋转轴向量，格式为\[向量，向量类型]。注：分子的旋转轴格式仅支持笛卡尔坐标。
*   `theta: list` 旋转角度，格式为\[角度，角度类型]，如：`[30, 'Degree']`，`[0.2, 'Radian']`
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度
*   `origin: list, optional` 旋转矢量的原点 (注意，它是旋转轴的原点，而不是轴上的一个点), 格式为\[坐标，坐标类型]，例如：
          [0.1, 0.0, 0.0, 'Direct']
          [0.1, 0.0, 0.0]
          [5.234, 0.0, 0.0, 'Cartesian']

***translation(atoms, direction, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
对选定的原子进行平移操作。

*   `atoms: array-like` 需要平移的原子的列表数组，数组的每个原子可以为以下形式：
    a. 原子的实例化对象，如：\[ *atom0, atom1, atom2* ];
    b. 原子的标准格式化数组，其格式为：\[元素名，坐标，坐标类型];
*   `direction: list`：平移方向向量，格式为\[坐标，坐标类型]
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***perturb(cutoff=0.1, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
对结构中的原子进行随机扰动。

*   `cutoff: float, default: 0.1` 扰动的截断距离，单位为埃(Å)
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

***constraint(self, atoms, isPersist=False, isConstraint_of_remainder=True, \*\*kwargs)***
对结构中的选择的原子进行固定(对应POSCAR的`selected dynamics`标签)

*   `atoms: array-like` 需要更新固定的原子的列表数组，数组的每个原子可以为以下形式：
    a. 原子的实例化对象，如：\[ *atom0, atom1, atom2* ];
    b. 原子的标准格式化数组，其格式为：\[元素名，坐标，坐标类型];
    c. 包含固定信息的原子的格式化数组，其格式为：\[元素名，坐标，坐标类型，固定信息]; 
    （注意：如果使用这里的信息，则不需要传入`constraints`参数）
*   `constraints: array-like` 原子固定信息，可以设置为以下形式：
    a. 单个bool值，如`True/False`，为所有输入原子设置相同的固定信息
    b. bool列表，长度与原子列表相同，为每个输入原子独立设置固定信息
    例如`[True,True,False,...]`（三方向固定信息相同）；
    或`[[True,True,False], [True,True,False], ...]`（三方向固定信息不同）
*   `isConstraint_of_remainder: bool, default: True` 是否更新未指定部分的原子固定信息
*   `constraint_of_remainder: bool/list, default: True` 用于指定未指定部分的原子固定信息


***getUnit(unit, tolerance=0.1, \*\*kwargs)***
获取指定区域的格式化原子信息。

*   `unit` 指定结构区域，其格式有两种：
    a. 沿着晶胞基矢的选取一定范围，格式为\[起点，终点，方向(0/1/2)]，其中0/1/2 分别代表x,y,z三个方向，
    如：\[0.234, 0.324, 2]
    b. 通过分别指定三个晶胞基矢方向的起始点，选中晶胞中的一个区域，其格式为3x2的数组，格式与示例如下：
          # 格式  [[x0, x1], [y0, y1], [z0, z1]]         
          # 示例  [[0.1, 0.2], [0.1, 0.2], [0.1, 0.2]]
    注意：只支持晶体结构对象，不可用于分子结构对象。
*   `tolerance: float, default: 0.1` 选取范围右侧边界处原子坐标的容差，其目的是选取原子在选取范围以外但是非常靠近右侧的原子（在一些情况下，原子存在微小扰动而偏离高对称位置，确保程序可以正确选中给定区域内的原子，避免调用该方法的其他结构操作方法，出现漏选或原子重叠现象的发生），单位为埃(Å)
*   `symbol_of_atoms: list, optional` 只选择在给定区域内的指定元素类型，其值为元素符号的列表数组，如\[ 'Na', 'Cl' ]

***removeUnit(unit, tolerance=0.1, isMoveAtoms=True, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
删除指定区域的原子。

*   `unit` 指定的范围，格式为\[起点，终点，方向(0/1/2)]，如：\[0.234, 0.324, 2]
    注意：只支持晶体结构对象，不可用于分子结构对象。
*   `tolerance: float, default: 0.1` 选取范围右侧边界处原子坐标的容差，其目的是选取原子在选取范围以外但是非常靠近右侧的原子（在一些情况下，原子存在微小扰动而偏离高对称位置，确保程序可以正确选中给定区域内的原子，避免调用该方法的其他结构操作方法，出现漏选或原子重叠现象的发生），单位为埃(Å)
*   `isMoveAtoms: bool, default: True` 删除指定区域的原子后，是否移动删除区域右侧的原子，填充移除单元之后的空位
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度
*   `isPersistLattice: bool, default: True`：是否在删除结构单原之后保持原有结构的晶胞参数。如果设为False，在删除结构单元后，晶胞基矢会沿着删除方向收缩相同长度的值

***addUnit(unit, nrepeat, tolerance=0.1, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
沿指定方向重复该区域内的结构单元。

*   `unit` 指定的范围，格式为\[起点，终点，方向(0/1/2)]，如：\[0.234, 0.324, 2]
    注意：只支持晶体结构对象，不可用于分子结构对象。
*   `nrepeat: int` 复制结构单元的次数。
*   `tolerance: float, default: 0.1` 选取范围右侧边界处原子坐标的容差，其目的是选取原子在选取范围以外但是非常靠近右侧的原子（在一些情况下，原子存在微小扰动而偏离高对称位置，确保程序可以正确选中给定区域内的原子，避免调用该方法的其他结构操作方法，出现漏选或原子重叠现象的发生），单位为埃(Å)
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度
*   `isPersistLattice: bool, default: True`：是否在删除结构单原之后保持原有结构的晶胞参数。如果设为False，在删除结构单元后，晶胞基矢会沿着删除方向收缩相同长度的值

***insertMolecule(structure\_of\_molecule, position\_in\_molecule, position, isUpdatedInfo=False, isPersist=False, \*\*kwargs)***
在晶体结构中插入分子。分别选取分子和晶体坐标系中一个参考点，计算两个参考点的距离差作为平移的矢量，实现在晶体中插入分子结构。
注意：只支持晶体结构对象，不可用于分子结构对象。

*   `structure_of_molecule` 分子的实例化对象
*   `position_in_molecule` 分子结构中的参考点，其格式为\[坐标, 'Cartesian']，如:
        [5.234, 0, 0, 'Cartesian']
*   `position` 晶体结构中的参考点，其格式为\[坐标，坐标类型]。例如：
        [0.1, 0, 0, 'Direct']
        [0.1, 0, 0]
        [5.234, 0.0, 0.0, 'Cartesian']
*   `isUpdatedInfo: bool, default: False`是否同步结构操作引起结构中其他关联信息的变化，如元素、化学式等
*   `isPersist: bool, default: Fasle` 是否保存结构到数据库中
*   `symprec: float, default: 1e-5` 寻找结构对称性时原子位置的误差精度
*   `angle_tolerance: float, default: -1.0` 寻找结构对称性时基矢间角度的误差精度

下面以构造二维四方相钙钛矿为例，演示结构操作函数的使用。

![sf](https://note.youdao.com/yws/api/personal/file/6C2876023B974361B114B9E9425DFAB7?method=download\&shareKey=5fd7ed3d8dd8abaa014339078f733e5f)

# 4. 高通量计算流程

本章将介绍JAMIP如何实现高通量计算任务的创建和流程管理。通过本章节的阅读，您可以了解以下内容：

*   高通量计算的任务流程与参数设置
*   计算任务的流程细节

## 4.1 任务流程简介

任务( task )是JAMIP进行DFT计算的基本单元，每个任务对应特定的计算需求，通过一次或多次计算实现。下面将简单介绍JAMIP目前已经实现的计算任务流程。

### 4.1.1 参数设置

JAMIP的运行配置文件包含以下四个文件，用户可以通过修改提交目录下的这些文件，动态地设置本次计算的参数：

| filename | function |
| -------- | -------- |
| input.py | 任务控制文件   |
| .incar   | 计算参数文件   |
| .cluster | 集群参数文件   |
| .link    | 任务依赖参数文件 |
| .extra   | 结构参数文件   |

其中`input.py`可通过`jp -i [software]`命令生成模板，如：

    jp -i vasp # 用于VASP计算任务的提交
    jp -i qe # 用于Quantum Espresso计算任务的提交

其他文件将在用户第一次执行 jp -r prepare 后，生成模板。

#### 第一性原理计算参数

##### 任务控制文件中的通用设置

```c
1. program 
 使用程序的路径，如
 vasp.program = '/share/apps/vasp/vasp5.4.1/bin/vasp_std'
 # 如果用户使用vasp计算，希望在计算中切换vasp程序，可以设置：
 > vasp.program = {'std': '/share/vasp6/bin/vasp_std',
                   'ncl': '/share/vasp6/bin/vasp_ncl'}
 # 对于类似于QE，计算中涉及多种可执行程序的软件，输入bin即可：
 > qe.program = '/share/apps/qe-6.6/bin'
 
2. potential 
 赝势库目录，如
 vasp.potential = '/share/apps/vasp/paw_pbe'
 # 赝势库的形式与不同软件所采用的命名规则有关，如vasp的赝势库是以元素命名的文件夹，
 # QE则直接是全部赝势文件，通过文件命名确定元素和赝势类型
 # 针对VASP赝势库中，一种元素对应多种赝势的情况，如果用户希望选用元素的指定赝势，可以在路径后添加映射字典，如：
 > vasp.potential = '/share/apps/vasp/paw', {'Si':'Si_d','Mg':'Mg_pv'}

3. tasks
 计算任务，任务名之间使用空格分隔，例如
 vasp.tasks = 'relax scf band dos optics'
 # 关于当前软件支持的任务，请参阅：控制文件实例或继续阅读后续内容
 
4. xc_func
 计算使用的参数集，包含交换关联泛函、soc、ldau等。默认情况下，VASP计算仅使用PBE泛函，设置如下：
 vasp.xc_func = 'pbe'
 # 如果用户希望同时使用多种参数集，需要使用空格连接，例如
 > vasp.xc_func = 'hse soc ldau'
 # 如果用户输入soc, hse, gw，ldau等参数，JAMIP将自动在计算时中添加所需的特有计算参数
 # 注意：上述参数设置对全部计算生效，用户可以在.incar中修改参数集内容
 
5. magmom
 计算时使用的磁矩字典，例如（以CsPbI3为例）
 vasp.magmom = {'Cs':0, 'Pb':3, 'I':0}
 # 此时INCAR将设置为 MAGMOM = 1*0 1*3 3*0 
 # 默认情况下，JAMIP设置vasp.magmom=False，即不在INCAR中输出MAGMOM
 # 此时计算将使用VASP的默认值，将所有元素磁矩设置为1，等价于 MAGMOM = 5*1
 # 如果结构中出现了磁矩字典中未包含的元素，这些元素的磁矩也将使用1
 # 以CsPbI3为例，如果设置 vasp.magmom=True 或 vasp.magmom = {'Pb':3}
 # INCAR将分别显示 MAGMOM = 1*1 1*1 3*1 和 MAGMOM = 1*1 1*3 3*1
 # 注意：磁矩只能设置为整数值
 
6. vdw
 计算使用的vdw泛函类型，例如
 vasp.vdw = 'd3'
 # JAMIP支持的vdw泛函有: d2, d3, b86, b88, pbe, df2, revdf2, rvv10, revpbe, optpbe 
 # 在使用部分vdw泛函时（例如b86,b88,rvv10等），需要用户提供额外的核文件（vdw_kernel.bindat），设置如下
 > vasp.vdw = 'b86', '/public/apps/vasp/vdw_kernel.bindat'
 
7. energy
 设置能量的收敛值，例如
 vasp.energy = 1e-5
 # 在VASP程序中对应：EDIFF=1e-5，单位为：eV
 # 在QE程序中对应：etot_conv_thr，单位为：Ry
 
8. force
 设置力的收敛值，例如
 vasp.force = 1e-2
 # 在VASP程序中对应：EDIFFG=-1e-2，单位为：eV
 # 在QE程序中对应：forc_conv_thr，单位为：Ry
 
9. kpoints
 设置计算使用的K点。k点支持多种设置方法，例如
 # 1. kspacing模式，根据倒空间大小进行插点，输入值为K点在倒空间中的间隔
 > vasp.kpoints = 0.25
 # 2. Gamma模式或 Monkhorst模式，声明模式时提供首字母即可
 > vasp.kpoints = 'Gamma', '6 6 6' # 插点数 6,6,6 无偏移
 > vasp.kpoints = 'M','6 6 6 0.5 0.5 0.5' # 插点数 6,6,6 偏移量 0.5,0.5,0.5
 # 3. Line Model， 线性插点, 根据元组长度不同对应以下三种模式：
 vasp.kpoints = 'Line Model', (\ # "Line" + K点 + 插点数(可选，默认为30)
                 "0.0000 0.0000 0.0000 \Gamma",
                 "0.5000 0.0000 0.5000 X",
                 "0.5000 0.2500 0.7500 W",
                 "0.0000 0.0000 0.0000 \Gamma",
                 "0.5000 0.5000 0.5000 L"), 20
 vasp.kpoints = 'Line Model', (\ # "line" + 包含插点数的 K点, 参考QE
                 "0.0000 0.0000 0.0000 \Gamma 20",
                 "0.5000 0.0000 0.5000 X 20",
                 "0.5000 0.2500 0.7500 W 20",
                 "0.0000 0.0000 0.0000 \Gamma 1",
                 "0.5000 0.5000 0.5000 L 20")
 # 4. Reciprocal模式， 直接给出倒空间的全部 K点， 可参考IBZKPT
 # 如果不输入权值(第4个数字)，默认所有K点权重为 1 
 vasp.kpoints = "Reciprocal", (\
                 "0.0000 0.0000 0.0000 1",
                 "0.3333 0.0000 0.0000 6",
                 "0.3333 0.3333 0.0000 2",
                 "0.0000 0.0000 0.5000 1",
                 "0.3333 0.0000 0.5000 6",
                 "0.3333 0.3333 0.5000 2")
 
10. kpath
 为特定任务独立设置K点，设置方法与上节相同，应用范围可以查看对应的任务。例如
 vasp.kpath.band = 'Line Model',(\
                     "0.0000 0.0000 0.0000 \Gamma",
                     "0.5000 0.0000 0.5000 X",
                     "0.5000 0.2500 0.7500 W",
                     "0.0000 0.0000 0.0000 \Gamma",
                     "0.5000 0.5000 0.5000 L"), 20
 
11. nbands
 设置能带数或能带倍数，基准值来自自洽计算（SCF）。例如
 # 1. 直接设置nbands值
 > vasp.nbands = 300
 # 2. 设置相对scf的倍数，最大为3（默认值为1.2）
 > vasp.bands = 1.5
 # 在进行能带、光吸收等计算时，通常需要添加空带才能比较准确的计算导带的情况。
 # VASP的推荐值为1.2倍scf(能带计算)，QE为scf+4，请根据计算体系大小，设置合理的值。
 # 注意：该参数仅在电子结构计算和光学性质计算中有效
 
12. external_files
 计算所需的额外文件。每次计算开始时，将自动地复制这些文件到计算目录中，如
 vasp.external_files = '~/.jamip/utils/vdw_kernel.bindat'
 # 如果需要复制多个路径，用逗号隔开即可，例如
 vasp.external_files = '~/.jamip/utils/vdw_kernel.bindat', '~/script/cbvb.x'
```

##### 任务控制文件（input.py）中，用于文件准备的相关函数

```python
> set_structure(input,output) 
- input：输入结构文件目录
- output：输出计算文件目录
> 读取结构文件，生成任务池中的计算实例
 
> set_extra()
> 根据结构生成.extra模板文件

> set_potential()
> 根据结构生成预计使用赝势文件 .potential， 后续计算将根据该文件生成赝势
 
> save(path)
- path：任务池保存路径
> 保存任务池文件
 
> Prepare.cluster(name) 
- name：作业管理系统的名称，如`pbs`,`lsf`,`sbatch`
> 生成或检查集群参数文件`.cluster`
 
> Prepare.incar(vasp) 
- vasp：VASP参数类
> 生成或检查计算参数文件`.incar`

> Prepare.links(vasp)
- vasp：VASP参数类
> 生成任务关联文件`.link`

```

#### 集群管理参数

在JAMIP中，集群参数设置主要依靠`.cluster`文件，基于作业提交模板生成提交文件，并在计算节点上开展并行计算。
用户也可以在提交任务时通过命令行设置集群参数，详见 jp命令。例如:

    jp -r qsub -f [pool] --cores 15 (使用15核进行计算)

在任务提交后，用户仍可以修改`.cluster`文件，实现计算资源动态调控。参数修改将在下一个任务启动时生效。

##### 通用设置参数

| 属性        |                        |
| --------- | ---------------------- |
| manager   | 集群的作业管理系统              |
| job\_name | 设置任务名                  |
| queue     | 使用队列名                  |
| nodes     | 使用节点数                  |
| cores     | 单节点使用核数，适用于PBS系统       |
| ntasks    | 总进程数，适用于LSF、SLURM系统    |
| maximum   | 队列中的最大任务数              |
| walltime  | 任务最大运行时间               |
| cmd       | 提交任务使用的命令              |
| mpi       | 并行计算程序使用的并行命令          |
| env       | 用于声明环境变量，如：编译器和python等 |
| user      | 提交任务的用户名，自动生成          |
| host      | 提交任务所在的主机，自动生成         |

##### 作业提交模板

```shell
#!/bin/bash
#PBS -N {{ job_name }}
#PBS -q {{ queue }}
#PBS -l nodes={{ nodes }}:ppn={{ cores }}
#PBS -l walltime={{ walltime }}
#PBS -o {{ output }}
#PBS -e .error

cd $PBS_O_WORKDIR

{% for line in env %}
{{ line }}
{% endfor %}

python3 {{ script }} {{ root }} {{ outdir }} {{ pool }} > .running
```

作业提交模板基于Jinja2语言，可以注意到模板中的变量名大部分与前面的参数字典对应。\
在JAMIP提交任务时，将从本地配置文件`.cluster`中读取集群参数，同任务信息一起传递到模板文件，在任务计算目录生成提交脚本`submit.sh`并提交。
如果用户希望自定义作业提交模板，可以参考 [Jinja2](https://jinja.palletsprojects.com/) 修改模板文件及集群参数文件，注意确保两者变量名称一致。

**mpi并行命令与核数：**\
如果并行命令为`mpirun`，JAMIP将补足为 `mpirun -np <sum_cores>`\
对于其他并行命令(例如`srun`)，JAMIP默认作业管理系统会自动完成并行进程管理，不需要补充参数\
关于上述总核数的获取，由于不同作业管理系统存在差异，JAMIP将优先使用`ntasks` (lsf, slurm)，如不存在则使用`nodes*cores` (pbs)

### 4.1.2 任务池管理与批量提交

![png](https://note.youdao.com/yws/api/personal/file/C9B9A8C7498B49B6988562A856B46206?method=download\&shareKey=41d2eb86e652910a2dbf6c91fdda4ce9)

##### 任务池文件说明

任务池由任务计算数据和任务状态信息两部分组成。其中，任务计算数据一般为`xxx.dat`文件，保存序列化的计算类，包含任务的计算内容、计算参数和结构信息。任务状态信息以dbm数据库的形式保存，命名为`.xxx.dat.dat`等。数据库中保存了任务的计算目录、状态和优先级，提交任务时将按照优先级顺序，依次提交任务池中状态为等待(W)的任务，并将其状态更新为运行(R)。当任务计算完成后，JAMIP将再次调用任务管理模块，将该任务状态更新为完成(C)。

##### 再次提交

由于JAMIP提交任务时仅提交状态为W的任务，如果用户希望重新提交之前计算过的任务，需要刷新任务池状态，以下是两种可选方式：

    1. jp -r prepare  重新生成任务池
    2. jp -c prepare -f <任务池>  根据各计算目录的状态信息，更新任务池文件

如果用户遇到大批量计算中有少数任务计算失败的情况(例如结构优化步数不够)，建议使用第二种方式提交，减少对队列的占用。

##### 多任务池与排队机制

在`.cluster`中的`maximum`参数设置了JAMIP从当前任务池提交到队列的最大任务数。当执行`jp -r qsub -f <poolfile>`时，如果任务池中待提交任务数充足，将提交`maximum`个任务到计算队列。当队列中JAMIP任务计算完成时，将从任务池中提交n个新任务，维持队列中正在计算和等待计算的任务总数为`maximum`。

对于JAMIP提交任务与非JAMIP任务、其他JAMIP任务池任务的计算优先级，通过`.cluster`中的`resubmit`参数设置，系统默认为`prior`

*   prior: 保证队列中JAMIP任务数等于maximum，即优先完成当前任务池
*   mini: 保证队列中JAMIP任务数不少于1的同时，使总任务数等于maximum，即优先完成队列中的其他任务

用户同时提交的多个任务池，将按提交至队列的先后顺序计算，任务池之间不会相互影响。

请注意，部分集群会限制用户最大提交的任务数。如果用户需要同时提交多个任务池，需要适当减少每个任务池的`maximum`。
`.cluster`仅在任务提交和计算开始时读取，用户可以通过修改`.cluster`的内容调整后续计算资源。例如将`maximum`参数修改为0，JAMIP将不会为当前任务池提交新的任务。

##### 子任务池

在部分JAMIP计算中，例如力常数、形变势等计算流程需要完成大量并行的计算任务，在单个计算节点可能需要较长时间。JAMIP支持为这些计算流程创建小型任务池，同时使用多个计算节点计算以加速计算流程。用户可以在支持并行计算的任务参数字典中设置`parallel`参数来开启该功能。`parallel`为最大并行数，若设置`parallel=1`或仅有一个任务需要计算，子任务仍将在当前计算节点上进行。

需要注意，子任务池不受上文中最大任务数`maximum`的限制，用户需要平衡设置`maximum`与`parallel`，避免子任务数爆炸。

当子任务全部计算完成后，完成最后子任务计算的计算节点将继续余下部分任务流程的计算。为了避免子流程和主流程的冲突(死循环)，我们设置主流程不会对当前子流程进行计算，同时删除任务池文件。

### 4.1.3 任务执行流程

本节将介绍在计算节点上，DFT程序的一般运行流程。

![png](https://note.youdao.com/yws/api/personal/file/B6B0B7B3E59F4B1D995DEEB16E1F498C?method=download\&shareKey=be7d8b14e9626e8030459461ccaa8493)

**1. 任务依赖**

在进行计算任务时，我们往往会按照一定的计算顺序，如结构优化 -> 自洽 -> 性质计算
在JAMIP中，我们使用字典来记录这种任务间的依赖关系，保存在`.link`文件中。例如：

    relax: []
    scf:
    -  relax
    band:
    -  scf
    hse_gap:
    -  scf
    -  band

在上面的示例文件中，relax无依赖，scf依赖relax，band依赖scf。对于hse\_gap这种多个依赖的任务，一般是第一个依赖项提供电荷波函数结构文件(scf)，最后一个提供其他性质或文件(band提供带边位置)。用户可以通过修改`.link`文件修改计算任务间的依赖关系，例如希望hse\_gap的带边信息从scf计算中获取，可以设置为

    hse_gap: 
    -  scf

JAMIP内部设置了稳健的任务依赖关系，因此用户通常不需要修改`.link`文件，用户可以查看`.link`获取并修改任务依赖。\
需要注意，与其他配置文件不同，`.link`会在每次`jp -r prepare`后重新生成，文件中的任务及依赖项必须全部包含在input.py的vasp.tasks中。

**2. 任务执行顺序**

在JAMIP内部，任务会被标记为以下几种状态

| 简写 | W  | H  | R  | C  | E  | D   |
| -- | -- | -- | -- | -- | -- | --- |
| 状态 | 等待 | 挂起 | 运行 | 完成 | 失败 | 纠错中 |

在全部计算开始前，JAMIP将从当前计算目录的`.status`获取目前任务完成状态，将完成的任务状态设置为C，未完成的设置为W，再将有依赖任务未完成的任务设置为H。对于全部等待的任务，将按用户在vasp.tasks中的输入顺序进行计算。当一个任务完成后，如果任务正确计算，JAMIP会将任务状态设置为C，递归的更新依赖该任务的状态，否则将任务状态设置为E。如果任务在计算过程中被纠错流程重新计算，JAMIP会将其任务状态设置为D，以避免纠错陷入死循环。
JAMIP通过`.status`文件唯一的判断计算任务是否完成。如果用户希望重新计算某些已被标记为完成的任务，可以在input.py内设置overwrite参数。例如：

    vasp.overwrite = 'scf band'

JAMIP将不会读取这些任务的完成状态，强制其重新计算

**3，文件继承**

在第一性原理计算时，通常需要拷贝之前自洽计算获得的结构、电荷密度、波函数文件进行性质计算。出于计算效率的考虑，如果用户没有在计算参数中设置`ICHARG`和`IWAVE`，JAMIP将使用VASP的默认值，即尽可能继承之前计算的CHGCAR和WAVECAR。
在生成计算输入文件时，可能存在以下情况：

*   当前计算明确不需要电荷密度/波函数，不复制这些文件
*   依赖计算中存在电荷密度/波函数，且当前计算也会输出这些文件，复制文件
*   依赖计算中存在电荷密度/波函数，且当前计算不会输出这些文件，复制文件的软链接
*   依赖计算中不存在电荷密度/波函数，当前计算可以不需要该文件，修改计算参数
*   依赖计算中不存在电荷密度/波函数，且当前计算明确需要该文件，计算失败

QE程序：
在进行结构优化时，输出目录均为： `qesave/relax.save`，QE程序将自动继承上一步的计算输出信息。同时，程序会基于xml文件来更新内存中的结构数据。
自洽场计算的输出目录为： `qesave/scf.save`，默认将不继承结构优化计算的波函数和电荷密度。
在进行性质计算时，JAMIP将复制 `qesave/scf.save` 目录下的文件到本次计算目录下，作为计算的初始信息，即默认将继承上步（SCF）输出的电荷密度与波函数

**4. 单任务流程**
![png](https://note.youdao.com/yws/api/personal/file/WEBd333fa173e0452b8ee1f3edc819dba89?method=download\&shareKey=c3cf9e8717a2ab226b54ee43e86cbb90)

**5. 计算参数更新**

在自动生成计算任务参数时，JAMIP将按照以下顺序进行设置：

*   从任务类加载参数字典 (.incar中的base字典+对应任务字典)
*   添加任务流程所需参数，如：设置 nbands, iband 等
*   更新组参数，如hse、gw、ldau、soc等
*   更新涉及输入文件的参数，如： encut, kspacing, istart 等

备注： 在计算程序开始时，JAMIP会将 input.py 中设置的收敛参数加入到 base 的字典中。

### 4.1.4 任务监控与纠错

VASP程序在运行过程中，可能由于参数设置不合理、文件准备不足等原因，计算任务会异常中断。
目前，JAMIP提供了VASP计算任务的纠错功能，能够根据JAMIP的输出日志内的错误信息，自动尝试调整计算参数等方案，纠正异常的计算任务。用户可以选择是否开启纠错功能，并且可以自由增添、修改错误集的内容。针对QE计算任务的纠错解决方案集正在更新中。

##### 监控模块

监控模块是计算流程中任务提交函数的一个装饰器，用户可以通过屏蔽该装饰器来关闭该监控功能
**代码链接-装饰器**： abtools/vasp/vaspflow\.py
**代码链接-监控模块**： abtools/vasp/monitor.py

     @Monitor
     def mpirun(self, incar, stdout):
         ...

在计算过程中，JAMIP会创建子线程执行VASP程序，而主线程负责监控任务运行。
程序会定期读取VASP程序的输出日志，检查文件中出现的错误关键词。正常情况下，子线程将在VASP计算完成后退出，主线程的监控器将在子线程停止活动后退出。当监控器发现错误时，将向并行计算程序（mpi）发出退出信号，子线程和监控器将依次退出，主线程将根据监控器返回的error属性，更新参数字典并进行纠错计算。
由于纠错计算中程序也会启动监控模块，为避免程序进入死循环，每个任务最多执行一次纠错计算，纠错时进行的参数修改对本次计算全局有效。

##### 集群检查

在计算程序启动前，JAMIP将检查计算节点的状态，确保高通量计算能够连续正常地进行
警告类：

1.  CPU核数是否与并行设置相符
2.  当前CPU占用是否超过90%
3.  当前内存占用是否超过90%
4.  节点上是否存在正在运行的并行程序
    退出类： 如果集群上存在VASP孤儿进程，将向这些进程发出退出信号

##### 纠错计算和纠错集设置

JAMIP将常用的纠错方案储存在 `~/.jamip/env/error.yaml`，每个纠错方案包含纠错名称、错误关键词和纠错参数。
用户可以根据自身需要，自由的添加和修改纠错集。以下是文件示例：

    NPAR:
    -  Please remove the tag NPAR from the INCAR
    -  npar: 
    NCL:
    -  non collinear calculations require that VASP is compiled
    - 
    EDIFF
    -  please rerun with smaller EDIFF
    -  ediff: ediff * 0.1

其中，NPAR纠错需要在INCAR中移除NPAR参数，因此设置纠错方案为`NPAR=None`，JAMIP将不再输出该参数。
NCL纠错需要使用`vasp_ncl`进行计算，需要通过修改`input.py`解决，无法自动解决，因此设置解决方案为空，此时将不再进行纠错，直接跳过该任务。
如果纠错方案中包含计算符，例如上面的第三个例子，JAMIP将自动查询并替换其中的字母部分。例如当前计算的EDIFF等于0.001，纠错后EDIFF将等于0.0001 。

### 4.1.5 计算结果提取与分析

使用jp命令可以实现简单的数据提取功能。目前，JAMIP支持批量提取计算数据/计算参数
（复杂或特定的数据提取活动，需要用户编写脚本）
**jp -o --output \[输出格式] \[输出性质] -f \[计算目录/任务池]**

*   **输出格式：** `form sort csv plot`
*   **输出性质：** Finder模块的单返回值方法和部分计算性质

**1. 路径输入判断**
通过`.status`（针对JAMIP）和`OUTCAR`（一般VASP计算）来判断输入目录是否为计算目录。
如果输入目录不是计算目录，将继续判断输入目录的子目录是否为计算目录。
如果未给程序指定任何目录，将使用当前目录作为输入值。

**2. 输出格式说明**

    I. csv格式说明：
    生成以逗号为分隔符的csv文件，保存标签；路径保存到最后一级
    对于出现无法正确读取数据的情况，程序将使用np.nan来进行补足
     
    $ jp -o csv free_energy -f TEST
     
    $ cat TEST.csv
    path,free_energy
    Si2.vasp,-43.40082825
    Si.vasp,-43.40082825
    II. sort格式说明：
    适用于少量数据的处理，根据所选属性的值对计算目录进行排列操作
     
    $ jp -o sort emass -f TEST
    +------------------+
    | Property: e-mass |
    +------------------+
    POSCAR2, 0.287
    POSCAR, 0.224
    +------------------+
    | Property: H-mass |
    +------------------+
    POSCAR2, 1.005
    POSCAR, 1.145
    III. form格式说明
    以表格形式输出属性值，方便用户直观地查看数据
    当jp -o命令未选择输出格式时，以此格式输出
    请适量控制输出属性的个数，以确保输出表格长度在单行字数限制以内，提高输出样式的可读性
     
    $ jp -o emass -f TEST 
    +---------+--------+--------+ 
    |  path   | e-mass | H-mass | 
    +---------+--------+--------+ 
    | POSCAR2 | 0.287  | 1.005  | 
    | POSCAR  | 0.224  | 1.145  | 
    +---------+--------+--------+ 
    IV. plot格式说明
    对数据进行快速地分布统计/关联性分析，适用于处理大量数据

**3. 支持输出性质**

| 计算性质           | 数据输出                                                |
| -------------- | --------------------------------------------------- |
| format         | 化学式(format)                                         |
| work\_function | 功函数(work\_function) （注：需要VASP计算真空能级且真空层在z方向）        |
| bandgap        | 带隙值(bandgap)，是否为直接带隙(isdirect)                      |
| emass          | 空穴有效质量(H-mass)，电子有效质量(e-mass)（注：有效质量为取几何平均获得平均值）    |
| dielectric     | 电子部分的介电常数(dielectric)，离子部分的介电常数(dielectric-ion)     |
| cbvb           | 带隙(bandgap)，价带顶(vbm-kpoint)，导带顶(cbm-kpoint)         |
| boltztrap      | 空穴有效质量(H-mass)，电子有效质量(e-mass)（注：调用boltztrap程序的计算结果） |

| 数据类型  | 计算参数                                                                 |
| ----- | -------------------------------------------------------------------- |
| int   | nkdim, nedos, nbands, nkpts, istart, icharg, ispin, nelm, nsw, nfree |
|       | lmaxmix ,ibrion, isif, isym, pstress, nelect, ismear, ialgo, lorbit  |
| float | encut, ediff, ediffg, cshift, potim, emin, emax, sigma,volume        |
|       | free\_energy,energy\_without\_entropy,fermi\_energy,max\_force       |
| str   | prec, gga, point\_group, datetime,vasp\_version,date                 |
| bool  | lsorbit, lwave, lcharg, lvtot, lelf                                  |

### 4.1.6 计算结果存储

用户可参阅上一章节，将计算结果储存到csv文件或数据库中。

**数据存储命令：**
**jp -o csv free\_energy fermi\_energy ... -f \[path]** 批量导出为csv文件
**jp --db entry -f \[path]** 批量存储计算结果
**jp --db structure -f \[path]** 批量存储结构文件
当未指定存储路径时，将使用当前目录作为输入目录

**数据存储函数：**

    from jamip.db.connect import Connect #初始化django连接
    import os
     
    # 将计算数据存储到数据库中
    db = Connect() # 实例化类
    properties = ['calculated_parameters','energy','bandgap','boltztrap',
     'born_effective_charge'] 
    db.load_entry('TEST/Si.vasp',properties) # 保存Si.vasp目录下的计算数据
    # 输入路径可以是：任务池、计算根目录或计算父目录(包含多个根目录)
     
    # 将结构文件存储到数据库中
    db = Connect()
    db.load_structure('test') # 保存文件夹内的全部结构文件
    # 通过文件名判断是否为结构文件及其数据类型，请确保文件名的合理命名。


## 4.2 基于VASP软件的高通量计算任务流程

任务(*task*)是JAMIP进行DFT计算的基本单元，每个任务对应特定的计算需求，通过一次或多次VASP计算实现。下面将介绍JAMIP目前所有已实现的计算任务流程。

### 4.2.1 自洽场计算与结构优化

#### 自洽场计算

**任务名：** `scf`
**任务依赖：** `relax/None` (根据relax任务是否存在自动确定)

自洽场计算是VASP计算的基础，主要提供以下功能：

1.  计算部分性质的准确值，如形成能、真空能级等
2.  输出电荷密度( CHGCAR )，波函数( WAVECAR )文件，用于后续的非自洽计算。

#### 结构优化

**任务名：** `relax`
**其他任务名：** `shape volume ions` (根据优化自由度，自动设置优化方案)
**任务依赖：** `None`

VASP通过ISIF参数控制结构优化的自由度(离子位置，单元体积和单元形状)。默认情况下，JAMIP进行全放开优化( 在`.incar`内设置`ISIF=3`)。
如果`.incar`的任务字典未设置ISIF参数，用户可使用任务自由度指定任务名。例如:

    vasp.tasks = 'ions'   # 仅优化离子自由度，即ISIF=2

在执行结构优化任务时，单次VASP计算往往不能到达预期的收敛标准，而增加步长可能在错误结构上浪费更多时间。
JAMIP支持下述优化方案：

*   首先，进行若干步低精度的结构优化，使结构快速弛豫到平衡位置附近
*   然后，进行有限步数的正常精度优化，直至结构到达收敛标准或优化步数到达上限。
    根据我们我们长期的研究经验，采取分步优化、逐渐提高计算精度参数的方案，可以显著缩短结构优化的时间。

默认情况下，JAMIP进行两次粗优化(精度逐渐增加)，至多三次标准精度的优化。如果全部优化计算结束后，计算仍未到达设定的收敛标准，视为结构优化任务失败，JAMIP将不再进行其他依赖于结构优化结果的计算任务。

    # input设置参数
    vasp.tasks = 'relax'     
    vasp.accelerate = True   # 开启粗优化计算，默认关闭
    vasp.accelerate = [{"kspacing":0.5,"ediff":1e-3,"istart":0,"nsw":20}, 
                       {"kspacing":0.3,"ediff":1e-4,"ediffg":-0.05,"nsw":20}]
    # 开启粗优化并设置粗优化参数, 列表内的字典对应优化次数和每步参数，这里展示的是粗优化的默认参数
    vasp.optcell = '1 0 0'   # 生成OPTCELL，可以在结构优化过程中，固定指定方向的晶胞参数保持不变
    # 1 0 0 分别对应xyz三个方向，1代表优化该方向的晶胞参数，0代表固定该方向的晶胞参数

**分步优化简述：**
在开展结构优化的实际操作中，不同结构优化至收敛所需的步数不同，部分结构的初态结构与平衡结构之间相差较大，如果仅使用高精度的结构优化，可能需要非常长时间才能弛豫到平衡位置。采用分步优化的策略，逐渐提高计算精度，可以加速收敛过程。
通常情况下，用户可以通过降低k点密度、能量和力的收敛值，实现低精度优化。以VASP计算为例，默认的粗优化参数可设置为：

    step1 : (kspacing=0.5, ediff=1e-3, istart=1, nsw=20)
    step2 : (kspacing=0.4, ediff=1e-4, ediffg=-0.05, nsw=20)

JAMIP在`relax/S0`目录下进行全部的粗优化计算(标准精度在S1-S3)，每步计算后将对CONTCAR和OUTCAR文件进行备份。
如果用户开启了粗优化，无论在粗优化过程中计算是否收敛，程序都将进行至少一步标准精度优化计算。因此不建议为粗优化设置高于正常精度的收敛标准。
如果用户确定计算结构非常接近平衡结构，可以考虑关闭粗优化功能，减少计算次数，节省计算时间。
**补充说明：**

*   在批量计算时，可能出现部分结构未收敛的情况，用户可以参考算例中的方案优化，制定计算流程
*   使用JAMIP数据库的结构操作方法，可以实现批量设置结构中离子的优化自由度(`Selective dynamics`)
*   添加`OPTCELL`可以在优化过程中固定指定方向的晶胞参数（注：仅适用于针对该方法进行预先特殊编译的VASP版本）。
    如果是使用`ioptcell`的vasp版本，用户可直接在`.incar`文件中的对应任务设置。

#### Hubbard U修正

一般认为，d和f电子的DFT误差的主要来源是它们的相关性质。DFT+U方法是一种常用的改进 d 和 f 电子描述的临时方法，其中添加“现场”电位以在强相关电子之间引入原子内相互作用。在VASP中，LDAUTYPE=2 对应 Dudarev 等人提出的势，其形式为：


![png](https://note.youdao.com/yws/api/personal/file/WEBa5625dd22c493378856fc95ef1b551f2?method=download&shareKey=e359705d5d72c79e34778e69e2580b92)

其中 U 和 J 分别是有效的库仑参数和交换参数，n 是具有自旋σ的 d 轨道数 m 的占用数。 原则上，U 和 J 可以根据第一性原理计算。然而，在现实中，U 和 J 的理论值给出的结果很差，因此，这些参数是通过拟合实验数据（例如氧化物带隙或晶格参数）来调整的。
U值来源[https://www.sciencedirect.com/science/article/pii/S0927025611001133]

因为方程只取决于差值 U – J，通常用变量 `$U_{eff}$` 代替 `U – J`。
在JAMIP计算中，默认设置元素的LDAUU=`$U_{eff}$`，LDAUJ=0，LDAUL和LMAXMIX根据元素自动确定。
用户通过在input.py中设置 `vasp.xc_func = 'ldau'` 或在.incar的参数字典中添加`ldau: True` 

**JAMIP生成的参数模板 (以FeO为例)**
```
LDAU = True
LDAUTYPE = 2
LDAUU = 4.0 0.0
LDAUJ = 0.0 0.0
LDAUL = 2 -1
LMAXMIX = 4
```

### 4.2.2 热力学性质

#### 分解焓

**任务名：** `decomposition`
批量计算该结构及其可能的分解产物的能量，给出其潜在分解路径及分解焓。当前，用户需要手动准备计算所需的所有晶体结构文件。后续更新将支持直接从JAMIP数据库中自动搜索获取相关的结构。

#### Convex hull

**任务名：** `convex`
二元相图分析。JAMIP将计算不同元素组成配比相对应它们单质的形成焓，构建二元相图。当前，用户需要手动准备计算所需的所有晶体结构文件。后续更新将支持直接从JAMIP数据库中自动搜索获取相关的结构。

#### Triangle zone

**任务名：** `triangle`
三元相分析。JAMIP将计算不同元素组成配比相对应它们单质的形成焓，构建三元相图。当前，用户需要手动准备计算所需的所有晶体结构文件。后续更新将支持直接从JAMIP数据库中自动搜索获取相关的结构。

### 4.2.3 电子结构

#### 能带结构

**任务名：** `band`
**任务依赖：** `scf`

计算沿指定高对称路径方向的能带结构。
在JAMIP计算任务中，HSE修正带隙、有效质量等计算，均需要根据能带计算结果来确定带边位置。
选择正确的高对称路径是获取可信的能带计算结果的先决条件。JAMIP默认基于晶体结构的空间群和晶格常数，自动确定高对称路径，路径选择参考了[seekpath](https://www.materialscloud.org/work/tools/seekpath)。用户也可选择在`input.py` 文件中手动指定高对称路径，如下所示：

    # input设置参数
    vasp.tasks = 'band'
    vasp.kpath.band = 'Line Model',(\
     "0.0000 0.0000 0.0000 \Gamma",
     "0.5000 0.0000 0.5000 X",
     "0.5000 0.2500 0.7500 W",
     "0.0000 0.0000 0.0000 \Gamma",
     "0.5000 0.5000 0.5000 L",
     "0.5000 0.2500 0.7500 W"), 20
    # 手动设置高对称路径，对任务池中的全部任务都有效
    vasp.band_insert = 30  # 设置插点数，默认为30
    vasp.band_split = True # 设置是否分段计算能带, 默认为False

用户可以通过 `jp -v kpath <structure_file>` 命令，在终端中快速查询指定晶体结构的空间群和推荐的高对称路径
当能带计算的总K点数较多时，可能导致内存不足的现象。JAMIP支持分段计算能带，用户可以根据计算实际情况选择是否启用该功能。

#### 电子态密度

**任务名：** `dos`
**任务依赖：** `scf`
电子态密度计算，获取各轨道电子的能量分布区间。

.incar内的dos参数：

    dos:
       lorbit: 11          # 决定DOSCAR和PROCAR文件的输出内容
       nedos: 3001         # 能量区间的插值数
       ismear: 0           # 高斯涂抹

如果计算获得的DOS图曲线不够光滑，可以尝试：设置 `ISMEAR=-5`、增大NEDOS或缩小态密度计算的能量区间（EMIN和EMAX的值）。

#### 能带分解电荷密度

**任务名：** `partchg`
**任务依赖：** `scf band`
计算价带与导带边处，电子在空间中的分布。计算分两步进行：

1.  从能带计算中提取带边位置，将其添加到网格K点后，执行一次包含带边的自洽计算
2.  根据自洽计算中带边K点位置和能带数，分别计算VBM和CBM处的部分电荷密度



计算完成后的目录结构：

    `-- electric
       `-- partchg
          |-- scf
          |-- cbm
          `-- vbm

自洽计算时，计算参数使用依赖任务的参数，K点网格根据当前任务的kpoints确定。
带边位置由能带计算结果来确定，当计算的晶体结构中不存在带隙时，该计算不会执行
计算依赖正确且收敛的WAVECAR文件

#### STM图拟合计算

**任务名：** `stm`
**任务依赖：** `scf`
计算带边附近一定能量区间内的能带分解电荷密度，可用于模拟扫描电镜图

.incar内的stm参数

    stm:
       lpard: true      # 是否计算能带分解电荷密度
       nbmod: -3        # 控制使用那些带计算分解电荷密度
       eint: -0.1       # 部分电荷密度的能带的能量范围

#### 形变势

**任务名：** `deformation`
**任务依赖：** `scf band`

```math
E_{d} = \frac {\partial E_{edge}}  {\partial (\Delta a/a_0)}
```

计算在价带顶和导带底的能量对应变的一阶导数，其中对带边能量值的比较需要进行能带对齐，材料结构需要建成正交晶胞。
为了计算应变后的带边能量，JAMIP直接从依赖任务中获取带边所在的K点位置(默认为band任务)，并添加到当前的K点网格中，进行一步自洽计算。
由于需要对带边能量进行对齐，用户需要根据材料维度选择添加以下参数：

*   **LVTOT/LVHAR**
    适用于2D材料，输出LOCPOT文件，将提取材料的真空能级并进行能带对齐。
*   **ICORELEVEL**
    适用于3D材料，在OUTCAR内输出各原子的轨道能级，可以选择其中一个深能级进行能带对齐。

.incar内的deformation参数：

    deformation:
       nsw: 0
       lvtot: true         # 输出LOCPOT
       icorelevel: 1       # 输出轨道能级
       axis: x y           # 设置计算的形变方向            
       scale: 0.99 0.995 1.0 1.005 1.01   # 设置形变方向的缩放比例
       parallel: 1         # 设置最大并行数

计算完成后的目录结构：

    `-- electric
        `-- deformation
            |-- 1
            |-- x-0.99
            |-- x-0.995
            |-- x-1.005
            |-- x-1.01
            |-- y-0.99
            |-- y-0.995
            |-- y-1.005
            `-- y-1.01

#### 杂化泛函相关计算

**任务名：** `hse_gap`
**任务依赖：** `scf band`

使用HSE泛函计算带隙。程序执行过程中，会将能带计算（如，PBE等）获得的带边位置添加到网格K点后，合并构成HSE带隙计算所需的KPOINTS文件。
带边位置由能带计算结果来确定，当计算的晶体结构不存在带隙时，该计算不会执行

**任务名：** `hse_band`
**任务依赖：** `scf`
使用HSE泛函计算能带结构，将低网格密度的K点路径添加网格K点后，合并构成HSE能带计算所需的KPOINTS文件。
.incar内的hse\_band参数：

    hse_band:
       mesh: 0.01  # K点的插值密度，插点数 = 倒格矢长度 / mesh

带边位置由能带计算结果来确定，当计算的晶体结构不存在带隙时，计算不会执行

#### 成键轨道分析

**任务名：** `cohp`
**任务依赖：** `scf`

使用lobster程序计算原子轨道耦合态密度
在计算时，需要先使用VASP进行一步态密度计算，再使用 lobster 计算轨道重叠布局COHP

**COHP**项目首页：<http://www.cohp.de/>
如果您在科学出版物中使用了相关计算结果，请引用以下内容：

    Crystal Orbital Hamilton Populations (COHP). Energy-Resolved Visualization of Chemical 
    Bonding in Solids based on Density-Functional Calculations. 
    R. Dronskowski, P. E. Blöchl, J. Phys. Chem. 1993, 97, 8617—8624.

    Crystal Orbital Hamilton Population (COHP) Analysis as Projected from Plane-Wave Basis Sets.
    V. L. Deringer, A. L. Tchougreeff, R. Dronskowski, J. Phys. Chem. A 2011, 115, 5461—5466.

    LOBSTER: A tool to extract chemical bonding from plane-wave based DFT.
    S. Maintz, V. L. Deringer, A. L. Tchougreeff, R. Dronskowski, J. Comput. Chem. 2016, 37, 1030—1035.

    Efficient Rotation of Local Basis Functions Using Real Spherical Harmonics.
    S. Maintz, M. Esser, R. Dronskowski, Acta Phys. Pol. B 2016, 47, 1165—1175.

在.incar文件中，用户可以设置cohp程序的输入参数：

    cohp:
     nedos: 3001              # DOS计算中，使用的vasp参数，可酌情添加
     basisSet: pbeVaspFit2015 # 使用的元素基集
     COHPstartEnergy: -20     # cohp计算的起始能量
     COHPendEnergy: 10        # cohp计算的终点能量
     orbitalwise: true        # 计算轨道耦合的PCOOP和PCOHP(默认为原子耦合)
     basisfunctions:          # 需要计算的元素及其轨道，不同元素需要分行添加
     - Si 3s 3p
     AtomsIndex: 1 5          # 计算cohp键合的原子序号
                              # 以上的能量范围、原子序号，可以自由修改

计算时，将在计算目录生成COHP的输入文件lobsterin：

    basisfunctions Si 3s 3p
    basisSet pbeVaspFit2015
    COHPstartEnergy -20
    COHPendEnergy 10
     
    cohpbetween atom 1 and atom 5 orbitalwise

#### 电荷布局分析

**任务名：** `bader`
利用bader程序计算原子的布局电荷，计算分两步进行:

1.  进行`LAECHG=True`的自洽计算，输出`AECCHG0 AECCHG2`, 合并为总的电荷密度文件，
2.  使用bader程序计算布局电荷
    **bader**项目首页：<http://theory.cm.utexas.edu/henkelman/research/bader/>
    如果您在科学出版物中使用了相关计算结果，请引用以下内容：

<!---->

    W. Tang, E. Sanville, and G. Henkelman 
    A grid-based Bader analysis algorithm without lattice bias, 
    J. Phys.: Condens. Matter 21, 084204 (2009).

    E. Sanville, S. D. Kenny, R. Smith, and G. Henkelman 
    An improved grid-based algorithm for Bader charge allocation, 
    J. Comp. Chem. 28, 899-908 (2007).

    G. Henkelman, A. Arnaldsson, and H. Jónsson, 
    A fast and robust algorithm for Bader decomposition of charge density, 
    Comput. Mater. Sci. 36, 354-360 (2006).

    M. Yu and D. R. Trinkle, 
    Accurate and efficient algorithm for Bader charge integration, 
    J. Chem. Phys. 134, 064111 (2011).

#### 能带反折叠

**任务名：** `unfolding`
基于原胞结构生成能带路径，程序将根据原胞与超胞之间的映射关系，将原胞中的K点映射到超胞中
(注：原胞的倒空间体积大于超胞)，待计算完成后，再将这些超胞能带点反折叠生成原胞能带，根据
波函数基组间的相似度确定置信度。计算流程如下：

    1. 读取超胞结构，使用spglib计算其原胞和转换矩阵，(或读取输入参数中的原胞和转换矩阵)
    2. 按原胞结构确定高对称路径，将高对称路径上的K点通过转换矩阵投影到超胞，
     输出KPOINTS，GPOINTS(每个K点的G格矢偏移量)，KPATH.in(高对称路径信息)
    3. 对超胞进行能带计算
    4. 使用后处理脚本绘制反折叠能带图 

.incar内的unfolding参数：

    unfolding:
       kmesh: 0.01 # 高对称路径在倒空间的插点间隔，0.01已足够进行分析
       dim: 2 2 2 # 可选参数，不使用spglib自动搜索晶胞，而是手动指定超胞大小
       primcell: /home/icsd/Si.vasp # 可选参数，与上一个参数共同使用。
       # 指定原胞结构文件的路径（需要输入绝对路径）

### 4.2.4 力学性质

#### 弹性模量及弹性常数

**任务名：** `elastic`
使用VASP自动计算弹性矩阵的功能(仅适用于三维结构)，可计算材料的弹性模量、体积模量和剪切
模量

#### 泊松比

**任务名：** `poisson`
通过改变初始结构的晶格常数，固定优化方向(若存在真空层则固定原子)，模拟单轴应变下，横截面
方向上的晶格常数变化
计算时将自动设置optcell来固定选中方向的晶格常数。 如果需要计算材料的泊松比方向等于3（即，
分别计算沿晶胞参数a、b和c方向的泊松比），优化时程序会分别沿着三个方向进行缩放，并固定该
方向的晶胞的晶胞参数，同时放开其他方向的晶胞参数，进行结构优化
如果计算的泊松比方向等于2，程序默认为该结构是二维材料。因此，程序会分别沿着指定的方向进
行缩放，同时该方向和真空层方向的晶胞参数将被固定住，只放开优化另一个方向的晶胞参数，进行
结构优化(axis内未出现的方向)

.incar内的poisson参数：

    poisson
       scale: 0.98 0.99 1.00 1.01 1.02 # 缩放系数
       axis: x y z                     # 需要计算的晶格方向
       parallel: 4                     # 并行计算节点数

### 4.2.5 光学性质

#### 光吸收谱相关计算

```math
I(\omega) = (\sqrt 2 \omega) [\sqrt {\epsilon_1(\omega)+\epsilon_2(\omega)}-\epsilon_1(\omega)]^{1/2}
```
其中 `$ \epsilon $`的单位是 1，`$\omega$`的单位是`$m^{-1}$`。VASP的光学计算可以获取不同能量下的介电常数，即`$E$`和`$ \epsilon $`已知，带入上式
```math
I(\omega) =  \sqrt 2E * e /(\hbar C) * [\sqrt {\epsilon_1(\omega)+\epsilon_2(\omega)}-\epsilon_1(\omega)]^{1/2} *1e^{-2}  \ \ \ \  (cm^{-1})

```

<!--```-->
<!--# 原子单位制向国际单位制转换-->
<!--BOLTZMANN_SI = 1.38064852e-23-->
<!--FINE_STRUCT = 7.2973525664e-3  # 精细结构常数 e2/(4πε0cħ)-->
<!--AVOGADRO = 6.022140857e23  # [1/mol]-->
<!--Clight_SI = 299792458.    # [m/s]-->
<!--a0_SI = 5.2917721067e-11  # [m]-->
<!--me_SI = 9.10938356e-31    # [kg]-->
<!--qe_SI = 1.6021766208e-19  # Electron Charge [C]-->
<!---------->
<!--# 国际单位制向原子单位制转换-->
<!--Clight = 1. / FINE_STRUCT-->
<!--EPSILON0 = 1. / (4. * math.pi)-->
<!--MU0 = 1. / (EPSILON0 * Clight**2)-->
<!--MUB = 1. / 2.-->

<!--Meter = 1. / a0_SI-->
<!--Kilogram = 1. / me_SI-->
<!--Coulomb = 1. / qe_SI-->
<!--Second = Clight_SI / Clight * Meter-->
<!--Newton = Kilogram * Meter / Second**2-->
<!--Joule = Newton * Meter-->
<!--Volt = Joule / Coulomb-->
<!--Ampere = Coulomb / Second-->
<!--Ohm = Volt / Ampere-->
<!--Siemens = Ampere / Volt-->
<!--hbar_SI = 1 / (Joule * Second)-->

<!--```-->

**任务名：** `optics`
光学性质计算。如果设置NPAR=1，VASP程序可以同时输出介电函数OPTIC，可用于计算吸收谱和跃迁强度

#### 介电常数

**任务名：** `dielectric`
计算电子和离子的介电函数

#### 激子结合能及波尔半径

**任务名：** `binding`
利用类氢Wannier-Mott模型，首先计算电子和空穴的平均有效质量以及材料的介电常数，代入公式可求得激子束缚能（`$E_B$`）：
```math
E_B = \mu^* R_y / m_0\epsilon^2_\alpha     \tag {1}  
```
其中，`$\mu^*$`为约化激子质量(即`$1 / \mu^* = 1/m^*_e + 1/m^*_h$`)，`$R_y$`为原子Rydberg能量，`$\epsilon_r$`为相对介电常数(晶格介电常数与电子介电常数之和)。
激子波尔半径`$a_{ex}$`可由如下公式计算：
```math
\alpha_{ex} = \alpha_H \epsilon_r m_0 / \mu^* \tag{2}
```
其中`$a_H$`是波尔半径。

#### 自陷态激子

**任务名：** `singlet`
计算单重态激子能量（注：该激子的激发电子和空穴的自旋方向相同）:

*   singlet计算需要读取scf计算的能带结果。需要先开展scf计算，然后才能执行singlet计算。
*   singlet计算前的scf计算，需要打开ispin = 2

**任务名：** `triplet`
计算三重态激子能量（注：该激子的激发电子和空穴的自旋方向相反）:
*   三重态激子的结构优化需要在激发态下进行

#### 非线性二次谐波成像

**任务名：** `shg`
计算材料的非线性二次谐波
正处在测试阶段，近期将提供支持
太阳能电池理论转换效率

**任务名：** `slme`
计算在黑体辐射条件下太阳能光伏材料的最大太阳能电池理论转换效率
正处在测试阶段，近期将提供支持

#### GW计算

**任务名：** `gw`
计算多体系统中的自能。需要先进行光学计算并输出波函数（WAVEDER）
正处在测试阶段，近期将提供支持

### 4.2.6 电输运性质

#### 载流子有效质量

```math
E = ak^2 + bk + c     \tag {1}
```
```math
m^* = \frac {\partial^2 E} {\partial k^2} = \frac {1} {2a} (m^2eV)=\frac {e\hbar^2} {2am_e} (1 m_e)   \tag {2}
```

**任务名：** `emass`
通过拟合在倒空间中正交的三个方向上带边曲率，计算带边位置电子和空隙的有效质量
（即能量对k点波矢量的二阶导的倒数）。
注意：如果带边附近严重偏离抛物线型能带，该计算方法将不适用。
默认带边位置由能带计算结果确定，当计算的晶体结构不存在带隙时，计算不会执行

**任务名：** `boltztrap`
计算电导有效质量。JAMIP需要调用Boltztrap程序，进行相关计算，计算中考虑了能带非抛物线特征、多带耦合等效应。
Boltztrap是由Georg Madsen和David J. Singh共同开发，程序中采用了玻尔兹曼半经典输运理论，通过对能带结构进行插值得到较密K点下的能带结构，进行材料相关输运性质的计算。
项目主页：<http://www.icams.de/content/research/software-development/boltztrap/>
本任务通过调用Boltztrap程序，计算材料的电导有效质量，如果您在科学出版物中使用了相关计算结果，请考虑引用以下内容：

    Madsen, G. K. H., and Singh, D. J. (2006).
    BoltzTraP. A code for calculating band-structure dependent quantities.
    Computer Physics Communications, 175, 67-71

#### 载流子迁移率计算(形变势理论)

二维载流子迁移率公式，其中`$C_{2D}$`为弹性模量，`$E_l$`是形变势常数，`$m*$`为载流子有效质量
```math
\mu = \frac { e \hbar^3 C_{2D}} {k_BT m^{*}m_d E_l^2}  \tag {1}
```
其中形变势和载流子有效质量的计算方法已在前面提到，弹性模量通过计算拉伸/压缩下的系统自由能变化获得，计算公式如下：
```math
C_{2D} = \frac {1} {S_0} \frac {\partial^2 E} {\partial (\Delta l/l_0)^2}     \tag {2}
```
同理，有二维载流子迁移率公式
```math
\mu = \frac { 2\sqrt{2} \pi e \hbar^4 C_{3D}} {3(k_BT)^{3/2}m^{*^{3/2}}E_l^2}  \tag {3}
```
其中弹性模量的计算公式为：
```math
C_{3D} = \frac {1} {V_0} \frac {\partial^2 E} {\partial (\Delta l/l_0)^2}     \tag {2}
```


**任务名：** `mobility`
采用形变势方法计算二维材料的载流子迁移率。首先，计算初始结构的能带结构获取带边位置；
其次，对材料的晶格常数沿着需要计算载流子迁移率的方向，进行晶格缩放`( 0.98,0.99,1.00,1.01,1.02 )`，
计算缩放后结构的VBM/CBM能级位置（注：需要采用真空能级，进行能带对齐）、以及带边处的有效质量；
最后，通过形变势公式计算得到材料的迁移率。

.incar文件中的mobility参数：

    mobility:
     scale: 0.98 0.99 1.00 1.01 1.02 # 晶胞缩放系数
     axis: x y z # 需要计算的载流子迁移率的方向

### 4.2.7 声子及热学性质

声子及热学计算基于Phonopy和Phono3py实现，在进行计算前请确保相关程序已正确安装：

    pip install phonopy phono3py

**Phonopy**项目首页：<http://phonopy.github.io/phonopy/index.html>
如果您在科学出版物中使用了相关计算结果，请引用以下内容：

    First principles phonon calculations in materials science,
    Atsushi Togo and Isao Tanaka, Scr. Mater., 108, 1-5 (2015)

#### 声子谱及声子态密度

**任务名：** `force`
力常数文件( FORCE\_SETS )是Phonopy进行性质计算的基础。
使用Phonopy生成一系列微扰后的超胞结构，提取超胞结构中的原子受力，构建出原子间的二阶力常数。
**任务流程：**

1.  使用自洽计算的结构和dim建立Phonopy类，生成超胞结构
2.  生成子任务池，准备计算输入文件，提交子任务池计算
3.  检查子任务池中的任务是否计算完成。如果完成，更新.status文件

在 .incar 文件的phonopy参数中，除设置VASP参数外，用户还需要设置以下参数：

    force:
       dim: 2 2 2 # 力常数计算所需的扩胞大小，也用于Gruneisen常数计算时指定扩胞大小（共用计算）
       symprec: 1e-3 # Phonopy寻找结构对称性的精度，对全部 Phonopy计算有效。
       # 注：Phonopy中默认为1e-6。 大多数情况下，此精度过高，在一些低对称体系中，
       # 会产生大量需要计算的超胞结构，默认精度设定为1e-3，可以加快这些体系的声子计算。
       parallel: 1 # 并行节点数

如果后续计算需要获取结构的力常数，程序将自动在计算根目录下生成FORCES\_SETS文件的备份

#### 软模相变

**任务名：** `softmode`
沿着声子谱中虚频的方向移动原子，寻找体系能量最低点，通过消除所有的虚频，可以实现找到声子
谱稳定的结构
注意：移动的软模需要保证在位于声子q点的布里渊区以内。所以，如果移动的软模声子为布里渊区
边界上，需要沿着该方向扩胞，使软模声子的q点折叠到第一布里渊区以内。如果软模声子在Gamma
点上，做软膜相变时，无需对结构进行扩胞。
任务流程：

1.  使用自洽计算的结构和dim，建立Phonopy类，读取FORCE\_SETS，生成软模结构
2.  生成子任务池，准备计算输入文件，提交子任务池计算
3.  检查子任务池中的任务是否计算完成。如果完成，更新.status文件

<!---->

    softmode:
     dimension: 1 1 1 # 软模相变的扩胞大小
     q: 0 0 0 # 原点位置
     band_index: 0 # 能带序数
     amplitude: 0.0 15.0 0.5 # 软膜相变范围
     argument: 0 # 相位因子
     parallel: 1 # 并行节点数

#### gruneisen常数

**任务名：** `gruneisen`
通过改变初始结构的晶格常数（缩放晶胞参数），模拟温度效应导致的晶格体积膨胀/收缩现象（来
自于晶格动力学的非谐效应），计算该结构的声子频率随体积的变化率，求得gruneisen常数
**任务流程：**

1.  使用自洽计算的结构和缩放系数建立plus和minus两组结构，使用isif=4进行优化。
2.  使用优化后的结构和dim，建立Phonopy类，生成超胞结构
3.  检查子任务池中的任务是否计算完成。如果完成，更新.status文件

<!---->

     nsw: 50
     isif: 4
     ibrion: 2
     scale: 0.05 # 计算Gruneisen常数时晶胞的缩放系数
     parallel: 1 # 并行节点数

计算完成后，所有计算文件均保存在 phonon/gruneisen 目录下，文件夹结构如下：

    phonon
    |-- force # 力常数计算目录
    |-- softmode # 软模相变计算目录
    `-- gruneisen # Gruneisen计算目录
     |-- plus 
     | |-- relax # 优化目录
     | `-- force # 位移结构
     `-- minus
     |-- relax # 优化目录
     `-- force # 位移结构

#### 零点能

**任务名：** `zpe`
材料在0K下所有声子的基态能量的求和。

#### IR光谱

**任务名：** `ir_spectrum`
正处在测试阶段，近期将提供支持

#### Raman光谱

**任务名：** `raman_spectrum`
正处在测试阶段，近期将提供支持

#### 热导率

**任务名：** `thermal_conductivity`
正处在测试阶段，近期将提供支持

### 4.2.8 其他性质

#### XRD图谱

正处在测试阶段，近期将提供支持

#### Packing factor

正处在测试阶段，近期将提供支持

#### 径向分布函数

正处在测试阶段，近期将提供支持

#### 容差因子及八面体因子（钙钛矿结构）

正处在测试阶段，近期将提供支持

## 4.3 基于QE软件的高通量计算任务流程

在本节中，将介绍使用Quantum ESPRESSO进行DFT计算的流程。
在使用QE软件计算时，JAMIP将根据任务固定输出文件名( prefix )和输入/输出目录( outdir )。

#### 计算目录文件结构

    output/
    `-- Si.vasp
      |-- submit.sh # 提交脚本    
      |-- scf.in
      |-- scf.out
      |-- band.in
      |-- band.out
      |-- dos.in        # dos计算输入文件(非自洽部分)
      |-- dos.out   
      `-- dos           # 对于性质计算(输出大量文件)会建立独立目录
      |  |-- dos.dat    # dos计算结果
      |  |-- dos.in     # dos计算输入文件(绘图部分)
      │  `-- dos.out    
      `-- qesave # 计算临时文件目录，储存赝势、波函数、电荷密度等文件
        |-- dos.save # dos临时目录
        `-- scf.save # scf临时目录

#### input.py设置

    qe.program = "/public/apps/qe/bin"  # 由于qe可能调用多种计算程序，这里需要给出程序所在目录
    qe.ecutwfc = 45           # wfc encut setting 
    qe.ecutrho = 360          # rho encut setting 

### 4.3.1 自洽场计算与结构优化

#### 自洽场计算

**任务名：** scf

**任务依赖：** `relax/None` (根据relax任务是否存在自动确定)

通过自洽场计算获得基态电荷密度与波函数。

#### 结构优化

**任务名：** `relax/vc-relax`
**任务依赖：** `None`

结构优化的任务名继承自QE。其中， relax 表示仅优化原子位置，晶胞形状保持固定； vc-relax 表
示优化离子位置和晶胞参数同时可变。

### 4.2.2 电子结构

#### 能带结构

**任务名：** `band`
**任务依赖：** `scf`

能带结构计算。基于xml文件绘制能带图，故只需进行一次非自洽计算

#### 电子态密度

**任务名：** `dos`或`projwfc`
**任务依赖：** `scf`
QE的电子态密度计算需要分两步完成：

1.  加密K点的非自洽计算 (pw\.x)
2.  绘图计算 (dos.x/projwfc.x)

### 4.2.3 声子及热学性质

#### 力常数计算及声子谱

**任务名：** `phband`
QE的声子谱计算需要分三步完成：

1.  力常数计算 (ph.x)
2.  q2r.x
3.  计算声子谱 matdyn.x
## 4.4 基于Gaussian软件的高通量计算任务流程

### input.py参数

```python
gau.program = "g16"  # Gaussian 运行强烈的依赖环境变量设置，这里仅声明gaussian版本
gau.tasks = "opt geom=connectivity" # Gaussian 计算的任务部分，目前不会拆分任务计算
gau.xc_func = "b3lyp/6-31g(d,p)" # Gaussian 计算的势部分，目前会适用于所有任务
```

### .cluster 参数

    env:
    -  export PGI_FASTMATH_CPU=sandybridge       # 使用AMD芯片时需要设置
    -  export g16root=/public/apps               # Gaussian目录的父目录
    -  export GAUSS_SCRDIR=`pwd`/tmp             # 计算时临时文件位置
    -  source $g16root/g16/bsd/g16.profile

### .incar 参数

```
base:
  mem: 10GB                 # Gaussian的集群参数(%)与计算参数(#)写在一起
  nprocshared: 16           # 在生成gjf文件时按关键词自动拆分
opt:
  task: opt geom=connectivity   # 基于input.py 自动生成
  chk: ./opt.chk

```

### 4.4.1 自洽场计算与结构优化

#### 自洽场计算

**任务名：** `scf`

**任务依赖：** `relax/None` (根据relax任务是否存在自动确定)

#### 结构优化

**任务名：** `opt`
**任务依赖：** `None`

结构优化任务

# 7. 命令行工具

在shell环境下，JAMIP通过jp命令与用户进行交互，执行任务提交、任务检查、数据提取和绘图等各项功能。
在终端下，执行 jp -h 或 jp --help ，获得jp命令的支持信息
直接执行jp，获得jamip程序的安装路径。

### 7.1 任务提交

***jp -i --input \[soft]***
生成任务的提交脚本副本

*   **可选参数**： vasp, qe, win2k, abinit, pwscf, gaussian, plot
*   **代码链接**： jamip/cui/create.py
*   **使用示例**：
    `jp -i vasp` 生成vasp计算的提交脚本
    `jp -i plot` 生成绘图脚本

***jp -r --run \[command]***
任务提交命令

*   **可选参数**： prepare, qsub, single
*   **代码链接**： jamip/compute/launch.py
*   **使用示例**：
    `jp -r prepare`  调用`input.py`，生成任务池文件
    `jp -r qsub -f [pool]` 将任务池中的任务提交至集群
    `jp -r single -f [pool]` 使用本地机串行计算任务池中的任务

***jp -f --file \[file]***
指定当前命令使用的任务池或输入目录

***jp --\[cluster]***
集群参数设置命令，参数信息会保存在集群配置文件 .cluster 内

*   **可选参数**：
    **jp --cores [int]** 设置单节点使用核数
    **jp --queue [string]** 设置使用的集群队列
    **jp --num [int]** 设置最大提交任务数
    **jp --nodes [int]** 设置单任务使用节点数
*   **使用示例**：
    `jp -r qsub -f [pool] --queue=host3 --num=5`

### 7.2 任务检查
***jp -c --check [command]***
- **可选参数：** show, status, prepare, qstat, bjobs. squeue
- **使用示例：**
    **jp -c qstat** 查询当前用户队列中运行的计算目录
    **jp -c qstat -f [jobid]** 打印任务号为jobid的任务的计算目录
    **jp -c show -f [pool]** 以表格形式输出任务池完成状态
    **jp -c prepare -f [pool]** 调用程序的续算检查功能，更新任务池的任务完成状态 (基于`.status`文件)
    **jp -c status -f [pool]** 重新生成`.status`状态文件，并更新任务池的任务完成状态 (基于计算目录)
- **补充说明：**
任务池的状态更新流程为: `W > R > C` , 即如果计算任务在提交后中断，其状态将停留在 `R` 。
`jp -c prepare` 适用于任务池中完成了部分任务的计算，需要更新任务池并再次提交的情况。
`jp -c status` 适用于.status文件错误或缺失，需要重新生成的情况。(例如用户手动更改了计算目录)

### 7.3 数据处理

***jp -o --output  [输出格式] [输出性质+] -f [计算目录/任务池文件]***
JAMIP的数据检索工具，支持对计算目录中的性质进行批量查询，并以表格/排序/csv等多种格式输出

*   **可选参数**： csv, sort, form, hdf5, plot （当未指定时，默认使用form格式）
*   **代码链接**： jamip/cui/output.py
*   **使用示例**：
    *`jp -o csv bandgap free_energy`* 批量提取自由能和带隙数据，并保存在CSV文件中
    *`jp -o hdf5 -f [hdf5]`* 查看HDF5文件内保存的数据
*  **支持输出性质**
  
| **计算性质** | **数据输出**                                                                    |
| ---------- | -------------------------------------------------------------------------------- |
| formula     | 化学式(formula)                                                                   |
| bandgap    | 间接带隙(indirect)，直接带隙(direct)，是否为金属(ismetal)                          |
| dielectric | 电子部分的介电常数(dielectric)，离子部分的介电常数(dielectric-ion)               |
| cbvb       | 间接带隙(bandgap)，价带顶(vbm-kpoint)，导带顶(cbm-kpoint)                            |
| emass      | 空穴有效质量(H-mass)，电子有效质量(e-mass)（注：有效质量为取几何平均获得平均值） |
| boltztrap  | 空穴有效质量(H-mass)，电子有效质量(e-mass)（注：提取boltztrap程序的计算结果）    |
| deformation  | 空穴形变势(vbm-dp)，电子形变势(cbm-dp)     |
| work_function | 功函数(work_function)  |

*  **支持输出计算参数和简单性质**

| **数据类型**  | **计算参数**                                                  |
| ----- | -------------------------------------------------------------------- |
| int   | nkdim, nedos, nbands, nkpts, istart, icharg, ispin, nelm, nsw, nfree |
|       | lmaxmix ,ibrion, isif, isym, pstress, nelect, ismear, ialgo, lorbit  |
| float | encut, ediff, ediffg, cshift, potim, emin, emax, sigma,volume        |
|       | free_energy, energy_without_entropy, fermi_energy, eentro |
|       | external_pressure, pullay_stress,         |
| str   | prec, gga, point_group, date, datetime,vasp_version               |
| bool  | lsorbit, lwave, lcharg, lvtot, lelf          
*   **详细信息**：
```
1. 路径查询
JAMIP通过`.status(针对JAMIP)`和`OUTCAR(一般VASP计算)`判断输入路径是否为计算目录
如果输入目录不是计算目录，将对其子目录进行查询(至多一层)
如果未给程序指定任何目录，将当前目录作为输入值
对于JAMIP计算的目录，数据提取均使用固定的目录，即能带使用'electric/band'， 总能来自'scf'
如果用户需要从其他目录提取数据，可以在源码中添加自己的提交函数

2. 输出格式
=== csv 格式 ===
指定为csv格式时，JAMIP会将数据提取结果保存到以提交文件命名的csv文件中，例如
$ jp -o csv free_energy -f TEST
$ cat TEST.csv
    
path,free_energy
Si2.vasp,-43.40082825
Si.vasp,-43.40082825

=== form 格式 ===
默认格式，以表格形式将数据提取结果打印到屏幕上
$ jp -o emass -f TEST  
+----------+ ---------+ ---------+ 
|   path   |  e-mass  |  H-mass  | 
+----------+ ---------+ ---------+ 
| POSCAR2  |  0.287   |  1.005   | 
|  POSCAR  |  0.224   |  1.145   | 
+----------+ ---------+ ---------+ 

=== sort 格式 ===
以排序的形式列出计算结果(从小到大)，例如检查优化结果
$ jp -o sort free_energy -f relax

+-----------------------+
| Property: free_energy |
+-----------------------+
 relax/S3, -33.56501524
 relax/S2, -33.56141982
 relax/S1, -33.55055661
 
 === plot 格式 ===
 TODO： 针对特定的任务，以图的方式对数据进行分析
 例如提取有效质量、泊松比时，绘制拟合曲线图
```
    
    
***jp -v --vasp [command] -f \[files]***

*   **输入参数**： 操作命令与文件路径
*   **命令简介**： JAMIP的对vasp的支持程序
*   **代码链接**： jamip/cui/vasptools.py
*   **使用示例**：
    *`jp -v clean -f [pool]`* 清理计算目录内的文件(删除前有提示，用户可修改范围)
    *`jp -v bond -f [files]`* 分析结构的成键环境
    *`jp -v potcar -f [files]`* 批量生成赝势文件(首次执行需要输入路径，用户可以为元素指定赝势)
    *`jp -v kpath -f [files]`* 分析结构的高对称路径
    *`jp -v standard -f [pool]`* 读取结构文件，保存在cifs目录，可以用于批量转化文件或提取结构优化结果

***jp --phonon [command] -f [file]***
从JAMIP的计算结果创建声子相关计算的输入输出文件

*   **输入参数**： 操作命令与文件路径
*   **命令简介**： JAMIP的对phonopy、phono3py、Phonopy-Spectroscopy的支持程序
*   **代码链接**： jamip/cui/phonon.py
*   **使用示例**：
    *`jp --phonon build -f [pool]`* 重建phonopy的输入输出目录
    *`jp --phonon build3 -f [pool]`* 重建phono3py的输入输出目录
    *`jp --phonon raman -f [pool]`* 重建raman计算的输入输出目录
    *`jp --phonon gruneisen -f [pool]`* 提取并计算gruneisen常数
*   **详细信息**：
    JAMIP主要通过计算目录下的info.hdf5获取计算时的phonopy输入信息，
    生成的yaml文件已包含力常数信息，可直接用于绘制声子谱、gruneisen常数等
    对于phonopy，尝试生成`BORN`, `FORCE_SETS`, `phonopy_disp.yaml`
    对于phono3py，尝试生成`FORCES_FC3`, `phono3py_disp.yaml`
    对于Raman计算，尝试生成`Raman.yaml`
    对于gruneisen计算，尝试生成 `gruneisen` (需要在执行命令后输入mesh矩阵)


***jp --db [command]***

*   **可选参数**： structure, entry, history
*   **命令简介**： 将指定的计算数据存入数据库，或查看存入数据库的历史数据
*   **代码链接**： jamip/db/connect.py
```
# history命令使用实例
$ jp --db history
 name format natoms SG
0 Si.vasp Si8 8 216
([fileds]/all/none):bandgap
 name format natoms SG indirect direct
0 Si.vasp Si8 8 216 0.6829 0.7021
([fileds]/all/none):energy
 name format natoms SG indirect direct energy
0 Si.vasp Si8 8 216 0.6829 0.7021 -43.381044
([fileds]/all/none):all
['structure_id', 'name', 'calculated_parameters', 'path', 'energy', 'energy_per_formula', 
'energy_per_atom', 'bandgap', 'bandgap_img', 'corrected_bandgap', 'effective_mass_of_bandside', 
'optical_bandgap', 'dielectric_constant', 'born_effective_charge', 'exciton_binding_energy', 
'pressure', 'stress_tensor', 'elastic_constants', 'bulk_modulus', 'Raman_frequencies', 
'IR_frequencies']
([fileds]/all/none):
```
### 7.4 辅助工具
***jp --version***
查看JAMIP程序版本号

***jp --mysql [command]***
- **可选参数：** `initialize, start, shutdown`
- **命令简介：** 自动化完成mysql的初始化，启动和关闭
- **代码链接：** `jamip/cui/softmanage.py`
- **使用示例：**
`jp --mysql initialize` MySQL初始化 (需要按提示，手动登陆并修改密码)
`jp --mysql start` 启动MySQL程序
`jp --mysql shutdown` 关闭MySQL程序

***jp --django [command]***
自动化完成Django的配置和数据库迁移
- **代码链接：** `jamip/cui/softmanage.py`
- **使用示例：**
`jp --django mysql` 配置MySQL参数，交互式输入数据库名称、登陆等信息
`jp --django sqlite` 配置Sqlite3参数
`jp --django makemigrations` 根据数据库结构生成迁移文件
`jp --django migrate` 根据迁移文件将数据库结构导入数据库
`jp --django dumpdata` 数据库导出，生成jamip.json文件
`jp --django loaddata` 数据库导入，将选择的json文件导入数据库


**使用说明**：
使用数据库相关功能必须先完成数据库初始化，用户根据自身使用的数据库，执行以下命令：
1. 执行 `jp --django mysql` 或 `jp --django sqlite` 生成数据库连接文件( `$HOME/env/django.json` )
2. 执行 `jp --django makemigrations` 生成数据库迁移文件
3. 执行 `jp --django migrate` 生成数据库结构，Sqlite数据库保存位置为( `$HOME/bin/jamipdb` )
完成数据库配置后，可执行 `jp --db history` ，显示以下信息表示数据库初始化正常：
```
Query failed in table entry. Exit!
```
如果用户希望使用其他数据库，可根据Django语法修改数据库连接文件

