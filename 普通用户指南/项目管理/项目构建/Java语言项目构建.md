<h1><font color=#0d65b1>Java 语言项目构建</font></h1> 

<h2><font color=#0d65b1>使用条件</font></h2> 

<h3><font color=#0d65b1>源码要求</font></h3> 
<ul>
<li><p>编码语言：java</p></li>
<li><p>编译器：open jdk 或 oracle jdk</p></li>
<li><p>编译脚本：maven、gradle 或 ant</p></li>
<li><p>Dockerfile：为支持容器化部署而准备。如果不提供 dockerfile 进行 docker build，则需要在<code>Pipeline 流程参数配置</code>中做特别设置。</p></li>
</ul>

<h3><font color=#0d65b1>环境要求</font></h3> 
<p>确保有满足如下要求的构建(机器)节点。</p>
<ul>
<li><p>编译器：安装了指定版本的 java jdk，并且可执行 javac 命令。</p></li>
<li><p>脚本执行工具：安装了指定版本的maven（gradle 或 ant），并且相关命令可用(例如：mvn)。</p></li>
<li><p>Docker：docker build 可用。</p></li>
</ul>

<h2><font color=#0d65b1>配置-简单模式</font></h2> 
<p>如果待构建源码满足<code>源码要求</code>，只需在简单模式进行如下操作即可。</p>
<p>1. 选择 “流水线模板”。</p>
<p>2. 选择 “源码分支”。</p>
<p>3. 选择 “执行节点”。</p>
<img src="http://upload.ouliu.net/i/20171127180913a8wcp.png"  class="mark-l"/>

<h2><font color=#0d65b1>配置-高级模式</font></h2> 
<p>在使用简单模式不能充分满足需求时，可以使用高级模式，对 Pipeline进行个性化配置。</p>

<h3><font color=#0d65b1>构建变量</font></h3> 
<p>默认变量</p>
<table>
	<tr>
		<th>变量名</th>
		<th>默认值</th>
		<th>变量赋值建议</th>
	</tr>
	<tr>
		<td>cmdBaseDir</td>
		<td>开发-源代码管理时，定义的源码仓参数</td>
		<td>采用默认值</td>
	</tr>
	<tr>
		<td>buildCmd</td>
		<td>开发-源代码管理时，定义的源码仓参数</td>
		<td>采用默认值</td>
	</tr>	
	<tr>
		<td>SonarUrl</td>
		<td>CloudOS定义的系统配置</td>
		<td>采用默认值</td>
	</tr>
	<tr>
		<td>DockerImageRegistry</td>
		<td>CloudOS定义的系统配置</td>
		<td>采用默认值</td>
	</tr>
	<tr>
		<td>DockerBuildUrl</td>
		<td>CloudOS定义的系统配置</td>
		<td>采用默认值</td>
	</tr>
	<tr>
		<td>DockerfilePath</td>
		<td>默认为空</td>
		<td>根据实际情况填写</td>
	</tr>
</table>
<br>

<p>除了以上默认变量外，还可单击 “构建变量” 下的【新增】，以便在 Pipeline 配置时使用。</p>

<h3><font color=#0d65b1>Pipeline 流程参数配置</font></h3> 
<p>选择 “流水线模板” 后级显示流水线模板每个阶段及详情。</p>
<p><b>A</b>流程剪裁</p>
<p>默认此构建模板 Pipeline 配置了如下阶段：</p>
<table>
	<tr>
		<th>流水线阶段</th>
		<th>是否有默认配置</th>
	</tr>
	<tr>
		<td>更新代码</td>
		<td>是</td>
	</tr>
	<tr>
		<td>代码编译</td>
		<td>是</td>
	</tr>
	<tr>
		<td>代码检查</td>
		<td>是</td>
	</tr>
	<tr>
		<td>单元测试</td>
		<td>是</td>
	</tr>	
	<tr>
		<td>打包 (docker)</td>
		<td>是</td>
	</tr>
	<tr>
		<td>归档</td>
		<td>是</td>
	</tr>
	<tr>
		<td>部署(自动)</td>
		<td>否</td>
	</tr>
	<tr>
		<td>自动测试</td>
		<td>否</td>
	</tr>
</table>
<br>
<p>此流程可进行适当地裁剪适配（例如：不使用 docker 的构建场景，则可裁剪打包阶段，将 docker build 任务清除）。操作步骤如下：</p>
<p>1. 单击某个阶段下 “操作” 栏的【设置参数】。</p>
<p>2. 单击 “Task 配置” 下【移除】。清空 “Task 设置”，直至如图所示：</p>
<img src="http://upload.ouliu.net/i/2017112717532371j6k.png"/>
<p>单击【保存】即可实现此阶段清空（达到流程剪裁适配目的）。</p>

<p><b>B</b>配置参数</p>
<p>1. 单击某个阶段下 “操作” 栏的【设置参数】。</p>
<p>2. 单击 “Task 配置” 下【新增】。选择 Task 类型，输入任务的各参数关联值。</p>
<img src="http://upload.ouliu.net/i/20171127174111n29zw.png"/>
<p>3. 单击【保存】即完成设置。</p>
<blockquote><p>说明：</p>1. 一般来说，各任务 “Task配置” 使用默认参数即可。<br>2. 各阶段任务参数配置说明请参考<code>任务参数配置</code>。<br>3. 更新代码、代码编译、代码检查的任务，一般是标准化的，使用默认参数即可。</blockquote>


