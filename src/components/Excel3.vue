<template>
  <div>
		<div style="width: 100%">
			<div style="overflow: auto;float: left;" :class="{tableWrap1: true, clicked1: click}">
				<table border="1" cellspacing="0" width="150%" class="table1" @click="abc">
					<tr class="tableTitle">
						<th>时间</th>
						<th>姓名</th>
						<th colspan="3">地址</th>
						<th v-if="!click">哈哈</th>
						<th v-if="!click">嘿嘿</th>
					</tr>
					<template v-for="(item, index) in tableData">
						<tr :key="index" class="tableBody">
							<td>{{ item.date }}</td>
							<td rowspan="4" v-if="index==0">{{ item.name }}</td>
							<td>{{ item.address }}</td>
							<td v-if="!click">{{ item.address }}</td>
							<td v-if="!click">{{ item.address }}</td>
							<td v-if="!click">{{ item.address }}</td>
							<td v-if="!click">{{ item.address }}</td>
						</tr>
					</template>
				</table>
			</div>
			<div style="overflow: auto; float: left; width: 70%;" v-if="click">
				<table border="1" cellspacing="0" width="150%" class="table2">
					<tr class="tableTitle">
						<th v-if="!click">时间</th>
						<th v-if="!click">姓名</th>
						<th v-if="!click" colspan="3">地址</th>
						<th>哈哈</th>
						<th>嘿嘿</th>
					</tr>
					<template v-for="(item, index) in tableData">
						<tr :key="index" class="tableBody">
							<td v-if="!click">{{ item.date }}</td>
							<td v-if="!click">{{ item.name }}</td>
							<td v-if="!click">{{ item.address }}</td>
							<td>{{ item.address }}</td>
							<td>{{ item.address }}</td>
							<td>{{ item.address }}</td>
							<td>{{ item.address }}</td>
						</tr>
					</template>
				</table>
			</div>
			<p>点击后哈哈和嘿嘿会往前移，可用jQuery判断出当前点击的是第几列，然后根据父元素兄弟元素等，拿到th元素，再根据th的colspan属性值，减去前面table占用的值，补在后面table的th前面。</p>
		</div>
  </div>
</template>

<script>
export default {
  name: "excel",
  props: {
    msg: String
  },
  data() {
    return {
      tableData: [
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄"
        },
        {
          date: "2016-05-04",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄"
        },
        {
          date: "2016-05-07",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄"
        },
        {
          date: "2016-05-10",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄"
        }
      ],
      click: false
    };
  },
  mounted() {},
  methods: {
		abc(){
			this.click = !this.click
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.tableWrap1 {
	width: 100%;
}
.tableWrap1.clicked1 {
	width: 30%;
}
.tableWrap1.clicked1 .table1 {
	background-color: skyblue;
}
.table1 td, .table1 th, .table2 td, .table2 th {
	height: 30px;
}
</style>
