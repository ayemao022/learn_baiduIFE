<template>
  <div>
    <div style="overflow: auto">
      <table border="1" cellspacing="0" width="150%" class="table1">
        <tr class="tableTitle">
          <th>时间</th>
          <th>姓名</th>
          <th>地址</th>
          <th>地址</th>
          <th>地址</th>
          <th>地址</th>
          <th>地址</th>
        </tr>
        <template v-for="(item, index) in tableData">
          <tr :key="index" class="tableBody">
            <td>{{ item.date }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.address }}</td>
            <td>{{ item.address }}</td>
            <td>{{ item.address }}</td>
            <td>{{ item.address }}</td>
            <td>{{ item.address }}</td>
          </tr>
        </template>
      </table>
    </div>
    <hr style="margin: 50px 0" />
		<div style="width: 100%">
			<div style="overflow: auto;float: left;width: 30%">
				<table border="1" cellspacing="0" width="150%" class="table2" bgcolor="skyblue">
					<tr class="tableTitle">
						<th>时间</th>
						<th>姓名</th>
						<th>地址</th>
					</tr>
					<template v-for="(item, index) in tableData">
						<tr :key="index" class="tableBody">
							<td>{{ item.date }}</td>
							<td>{{ item.name }}</td>
							<td>{{ item.address }}</td>
						</tr>
					</template>
				</table>
			</div>
			<div style="overflow: auto; float: left; width: 70%;">
				<table border="1" cellspacing="0" width="150%" class="table3">
					<tr class="tableTitle">
						<th>地址</th>
						<th>地址</th>
						<th>地址</th>
						<th>地址</th>
					</tr>
					<template v-for="(item, index) in tableData">
						<tr :key="index" class="tableBody">
							<td>{{ item.address }}</td>
							<td>{{ item.address }}</td>
							<td>{{ item.address }}</td>
							<td>{{ item.address }}</td>
						</tr>
					</template>
				</table>
			</div>
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
      class1: false,
      left: ""
    };
  },
  mounted() {},
  methods: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
