<h1><font color=#0d65b1>KPI 配置</font></h1>
<p>1. 在<code>租户中心</code>中，单击左侧导航栏【租户管理】>【租户 KPI 配置】。</p>
<p>2. 可在右侧<code>设置阈值</code>栏，设置项目合格的标准。</p>
<img src="http://upload.ouliu.net/i/201711241108164our1.png"  class="mark-l"/>
<p>KPI 设置的阈值对应显示在<code>项目概览</code>中进度、敏捷、质量三个维度下的目标值。 KPI  配置说明如下：</p>
<table >
	<tr>
		<th>名称</th>
		<th>描述</th>
		<th>类型</th>
	</tr>
	<tr>
		<td >story.nointime.num</td>
		<td>没有及时完成的需求数量</td>
		<td class="title">敏捷</td>
	</tr>
	<tr>
		<td >task.nointime.num</td>
		<td>没有及时完成的任务数量</td>
		<td class="title">敏捷</td>
	</tr>
	<tr>
		<td>bug.nointime.num</td>
		<td>没有及时完成的缺陷数量</td>
		<td class="title">敏捷</td>
	</tr>	
	<tr>
		<td>story.intime.day</td>
		<td>要求的需求上市周期</td>
		<td class="title">敏捷</td>
	</tr>
	<tr>
		<td>task.intime.day</td>
		<td>任务完成周期</td>
		<td class="title">敏捷</td>
	</tr>
	<tr>
		<td>bug.intime.day</td>
		<td>要求的缺陷修复周期</td>
		<td class="title">敏捷</td>
	</tr>
	<tr>
		<td>story.intime.warn</td>
		<td>距离完成时间多少天，开始警示</td>
		<td class="title">进度</td>
	</tr>
	<tr>
		<td>task.intime.warn</td>
		<td>距离完成时间多少天，开始警示</td>
		<td class="title">进度</td>
	</tr>
	<tr>
		<td>bug.intime.warn</td>
		<td>距离完成时间多少天，开始警示</td>
		<td class="title">进度</td>
	</tr>
	<tr>
		<td>sonar.result</td>
		<td>代码检查检查是否合格</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>sonar.debt</td>
		<td>sonar检查出来的技术债务</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>sonar.duplication</td>
		<td>sonar检查出来的代码重复率(%)</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>sonar.complexity.max</td>
		<td>允许的最大圈复杂度</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>sonar.complexity.avg</td>
		<td>平均圈复杂度</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>sonar.debt.increase</td>
		<td>新代码允许导致技术债务最大增加多少</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>sonar.duplication.increase</td>
		<td>新代码允许导致重复代码最大增加多少</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>sonar.complexity.avg.increase</td>
		<td>新代码允许导致平均圈复杂度最大增加多少</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>build.result</td>
		<td>编译构建是否成功</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>ut.line.cov</td>
		<td>单元测试代码行覆盖率</td>
		<td class="title">质量</td>
	</tr>	
	<tr>
		<td>ut.method.cov</td>
		<td>单元测试方法覆盖率</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>st.cov</td>
		<td>每千行代码的用例数</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>bug.cov</td>
		<td>每千行代码的缺陷数</td>
		<td class="title">质量</td>
	</tr>
	<tr>
		<td>bug.noclosed</td>
		<td>发布前计算缺陷遗留率，以一般缺陷计算。需要加权计算，一个致命等于6个一般，一个严重等于3个一般，3个提示等于1个一般</td>
		<td class="title">质量</td>
	</tr>
</table>