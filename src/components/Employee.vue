<template>
  <div class="content">
    <!-- <div class="content-title" id="customer">
      <p style="    font-size: 22px;"><strong>Danh sách khách hàng</strong></p>
      <a href="#" @click="show = true">
        <img src="@/assets/add.png" />
        <span>Thêm khách hàng</span>
      </a>
    </div>
    <div class="content-search">
      <div class="input-search">
        <img src="@/assets/search.png" />
        <input placeholder="Tìm kiếm theo mã,tên khách hàng" />
      </div>
      <div class="reset">
        <a href="#"><img src="@/assets/refresh.png"/></a>
      </div>
    </div> -->
    <div class="content-header">
      <div class="content-header-left">
        <h4>Danh mục</h4>
        <img src="@/assets/icon/page-next.png" />
        <a href="#">Nhân viên</a>
        <span>Lọc nhanh</span>
        <select>
          <option value="">Đang làm việc</option>
        </select>
      </div>
      <div class="content-header-right">
        <button>Quay lại thiết lập ban đầu</button>
        <button><img src="@/assets/icon/viewEmail.png" />Phản hồi</button>
      </div>
    </div>
    <div class="list-emp">
      <table class="table table-striped" style="background-color:#EEEEEE">
        <thead style="border-right: 1px solid #ddd;">
          <tr class="table-action">
            <!-- <div @click="show = true"> -->

            <div @click.stop="showScheduleForm = true">
              <img src="@/assets/icon/SaveAdd16.png" />
              <span>Thêm</span>
            </div>
            <div>
              <img style="height:20px" src="@/assets/icon/icons8-view-64.png" />
              <span>Xem</span>
            </div>
            <div>
              <img src="@/assets/icon/Edit16.png" />
              <span>Sửa</span>
            </div>
            <div>
              <img src="@/assets/icon/icons8-delete-26.png" />
              <span>Xóa</span>
            </div>
            <div>
              <p class="sprite"></p>
              <span>Nạp</span>
            </div>
          </tr>
          <tr>
            <th scope="col">Tên đăng nhập</th>
            <th scope="col">Tên nhân viên</th>
            <th scope="col">Số điện thoai</th>
            <th scope="col">Ngày sinh</th>
            <th scope="col">Giới tính</th>
            <th scope="col">Trang thái làm việc</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in listEmploy.data" :key="item.EmployeeId">
            <td>{{ item.EmployeeCode }}</td>
            <td>{{ item.FullName }}</td>
            <td>{{ item.Gender }}</td>
            <td>{{ item.DateOfBirth }}</td>
            <td>{{ item.PhoneNumber }}</td>
            <td>{{ item.Email }}</td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="paging">
      <p>Hiển thị từ 1-10/1000 khách hàng</p>
      <div class="paging-index">
        <ul>
          <li><img src="@/assets/btn-firstpage.svg" /></li>
          <li><img src="@/assets/btn-prev-page.svg" /></li>
          <li class="paging-number">1</li>
          <li class="paging-number">2</li>
          <li class="paging-number paging-active">3</li>
          <li class="paging-number">4</li>
          <li class="paging-number">5</li>
          <li class="paging-number">6</li>
          <li><img src="@/assets/btn-next-page.svg" /></li>
          <li><img src="@/assets/btn-lastpage.svg" /></li>
        </ul>
      </div>
      <p>10 khách hàng trên/trang</p>
    </div>
    <EmployeeForm
      :visible="showScheduleForm"
      @close="showScheduleForm = false"
    />
  </div>
</template>
<script>
import axios from "axios";
import EmployeeForm from "./EmployeeForm.vue";
export default {
  components: {
    EmployeeForm,
  },
  data() {
    return {
      showScheduleForm: false,
      listEmploy: [],
    };
  },
  async mounted() {
    this.listEmploy = await axios.get(`http://api.manhnv.net/api/employees`);
    console.log(this.listEmploy);
  },

  methods: {
    editItem: function() {
      this.dialog = true;
    },
  },
};
</script>
<style scoped>
.sprite {
  background: url("../assets/icon/set-icon.png") no-repeat 0 -2586px;
  width: 16px;
  height: 13px;
}
.list-emp td,
th {
  border: 1px solid #ddd;
}
.list-emp th {
  text-align: center;
}
.list-emp {
  margin: 0px 8px;
}
.sprite {
  background-image: url("/assets/icon/set-icon.png") no-repeat;

  background-position: 0 -2586px;
  width: 16px;
  height: 13px;
}
.table-action div img {
  height: 20px;
}
.table-action {
  display: flex;
  padding: 8px;
  height: 40px;
}
.table-action div {
  display: flex;
  margin-left: 8px;
  padding: 0 4px;
}
.table-action div p {
  margin-top: 3px;
}
.table-action div span {
  padding-left: 8px;
}
.table-action :hover {
  background: #fff;
  /* border: 1px solid blue; */
}
.content {
  color: #333;
}
.content-header-right button {
  margin: 5px 5px;
}
.content-title {
  display: flex;
  justify-content: space-between;
  padding: 10px 20px;
}
.content-header {
  padding: 10px;
  display: flex;
  justify-content: space-between;
}
.content-header-left {
  display: flex;
}
.content-header-left img {
  height: 20px;
  margin: 6px;
}
.content-header-left span,
select {
  margin: 6px;
}
.content-header-left select {
  outline: none;
}

.content-header-left a {
  color: blue !important;
  margin: 6px;
}
#customer.content-title a {
  background-color: #019160;
  height: 38px;
  border-radius: 3px;
  color: #fff;
  padding: 8px 11px;
  margin-top: 13px;
}
.content-title a img {
  position: relative;
  top: -2px;
}
.content-search {
  display: flex;
  justify-content: space-between;
  padding: 0 20px;
  padding-bottom: 19px;
}
.input-search {
  height: 37px;
  position: relative;
  /* width: 21%; */
  width: 200px;
  border: solid 1px #bbbbbb;
  border-radius: 4px;
}
.input-search img {
  position: absolute;
  height: 18px;
  top: 8px;
  left: 7px;
}
.input-search input {
  outline: none;
  border: none;
  height: 34px;
  padding-top: 2px;
  width: 100%;
  padding-left: 30px;
}
.reset {
  height: 31px;
  width: 40px;
  border: solid 1px #bbbbbb;
  border-radius: 4px;
  position: relative;
}
.reset img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.content-list table {
  text-align: center;
  border-right: 5px solid #e5e5e5;
  border-bottom: 5px solid #777777;
}
.content-list {
  padding: 0 13px;
}
/* Phan trang */
.paging li {
  list-style: none;
}
.paging {
  display: flex;
  justify-content: space-between;
  padding: 0px 20px;
}
.paging ul {
  display: flex;
}
.paging-number {
  height: 30px;
  border: solid 1px #e8e8e8;
  /* height: 37px; */
  width: 28px;
  /* display: inline-block; */
  /* padding: 0px 6px; */
  margin: 0px 5px;
  text-align: center;
  border-radius: 50%;
  padding-top: 4px;
  background: #e5e5e5;
  position: relative;
  top: -3px;
}
.paging-active {
  background: #019160;
  color: #fff;
}
</style>
