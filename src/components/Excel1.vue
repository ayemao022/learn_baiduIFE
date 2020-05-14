<template>
  <div style="overflow: auto">
    <table border="1" cellspacing="0" width="150%" class="table">
      <tr class="tableTitle">
				<template class="titleFixed">
					<th :class="{fixed: class1}" class="date">时间</th>
					<th :class="{fixed: class1}" class="name">姓名</th>
					<th :class="{fixed: class1}" class="address">地址</th>
				</template>
        <th :class="{overflow: class1}" class="address" :style="left">地址</th>
        <th :class="{overflow: class1}" class="address" :style="left">地址</th>
        <th :class="{overflow: class1}" class="address" :style="left">地址</th>
        <th :class="{overflow: class1}" class="address" :style="left">地址</th>
      </tr>
      <template v-for="(item, index) in tableData">
        <tr :key="index" class="tableBody">
					<template class="bodyFixed">
						<td class="date" :class="{fixed: class1}" ref="a">{{ item.date }}</td>
						<td class="name" :class="{fixed: class1}" rowspan="4" v-if="index==0" ref="b">{{ item.name }}</td>
						<td class="address" :class="{fixed: class1}" rowspan="4" v-if="index==0" @click="abc(index)" ref="c">{{ item.address }}</td>
					</template>
          <td class="address" :class="{overflow: class1}" :style="left">{{ item.address }}</td>
          <td class="address" :class="{overflow: class1}" :style="left">{{ item.address }}</td>
          <td class="address" :class="{overflow: class1}" :style="left">{{ item.address }}</td>
          <td class="address" :class="{overflow: class1}" :style="left">{{ item.address }}</td>
        </tr>
      </template>
    </table>
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
			left: ''
    };
	},
	mounted () {
		// this.abc()
	},
	methods: {
		abc(index){
			console.log(window.getComputedStyle(this.$refs.c[index]).height);
			let aHeight = window.getComputedStyle(this.$refs.a[index]).height
			let aWidth = window.getComputedStyle(this.$refs.a[index]).width
			let bHeight = window.getComputedStyle(this.$refs.b[index]).height
			let bWidth = window.getComputedStyle(this.$refs.b[index]).width
			let cHeight = window.getComputedStyle(this.$refs.c[index]).height
			let cWidth = window.getComputedStyle(this.$refs.c[index]).width
			this.class1 = !this.class1
			this.$refs.a[index].style.height = aHeight
			this.$refs.a[index].style.width = aWidth

			this.$refs.b[index].style.height = bHeight
			this.$refs.b[index].style.width = bWidth
			this.$refs.b[index].style.marginLeft = aWidth

			this.$refs.c[index].style.height = cHeight
			this.$refs.c[index].style.width = cWidth
			this.$refs.c[index].style.marginLeft = (parseInt(aWidth) + parseInt(bWidth)) + 'px'
			this.left = 'left: ' + (parseInt(aWidth) +  parseInt(bWidth) + parseInt(cWidth)) + 'px'
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.table {
	position: relative;
}
.table td, .table th {
	height: 40px;
}
.table .fixed {
	position: fixed;
	background-color: skyblue;
}
.table .overflow {
	overflow: auto;
	/* float: right; */
}
</style>
