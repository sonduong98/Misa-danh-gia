<template>
  <div id="app1">
    <v-app id="inspire">
      <v-row justify="space-around">
        <v-col cols="auto">
          <v-dialog
            transition="dialog-top-transition"
            v-model="show"
            width="900"
          >
            <!-- <template v-slot:activator="{ on, attrs }">
              <v-btn color="primary" v-bind="attrs" v-on="on"
                >From the top</v-btn
              >
            </template> -->
            <template v-slot:default="dialog">
              <v-card style="border:solid 4px #0973b9;border-radius:0px">
                <v-toolbar
                  color="#0973b9"
                  style="height: 41px !important;background-color: rgb(9, 115, 185);border-color: rgb(9, 115, 185);padding: 0px;position:relative"
                  dark
                >
                  <div
                    @click="dialog.value = false"
                    style="    position: absolute;right: 0px;top: 0px;right: 8px;font-size: 24px;cursor: pointer;"
                  >
                    x
                  </div>
                </v-toolbar>
                <div
                  class="modal-action"
                  style="height:40px;background-color:#ededed;display:flex"
                >
                  <div @click="show = true">
                    <img src="@/assets/icon/SaveAdd16.png" />
                    <span>Thêm</span>
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
                </div>
                <div class="form-container">
                  <div class="form">
                    <div class="field">
                      <div class="label">
                        <span>Ma nhan vien</span>
                        <span class="required">(*)</span>
                      </div>
                      <div class="input small">
                        <input />
                      </div>
                      <em class="validate-msg">
                        Dùng làm tên đăng nhập vào hệ thống, có thể sử dụng số
                        điện thoại hoặc email cho dễ nhớ.
                      </em>
                    </div>
                    <div class="field">
                      <div class="label">
                        <span>Email</span>
                      </div>
                      <div class="input medium">
                        <input />
                      </div>
                    </div>
                    <div class="field">
                      <div class="label">
                        <span>So dien thoai</span>
                      </div>
                      <div class="input medium">
                        <input />
                      </div>
                    </div>
                    <div class="field">
                      <div class="label">
                        <span>Ho va ten</span>
                        <span class="required">(*)</span>
                      </div>
                      <div class="input large">
                        <input />
                      </div>
                    </div>

                    <div class="field-group">
                      <div class="groupLeft">
                        <div class="field">
                          <div class="label">
                            <span>Gioi tinh</span>
                          </div>
                          <div class="input large">
                            <input />
                          </div>
                        </div>
                      </div>
                      <div class="groupRight">
                        <div class="field">
                          <div class="label">
                            <span>Ngay sinh</span>
                          </div>
                          <div class="input large">
                            <input />
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="field">
                      <div class="label">
                        <span>Nơi cấp CMND</span>
                      </div>
                      <div class="input large">
                        <input />
                      </div>
                    </div>
                    <div class="field">
                      <div class="label">
                        <span>Phân quyền</span>
                        <span class="required">(*)</span>
                      </div>
                      <div class="checkbox">
                        <div class="checkbox-item">
                          <input
                            type="checkbox"
                            id="vehicle1"
                            name="vehicle1"
                            value="Bike"
                            class="input-checkbox"
                          />
                          <label for="vehicle1"
                            >Vai trò Quản trị hệ thống</label
                          >
                        </div>
                        <div class="checkbox-item">
                          <input
                            type="checkbox"
                            id="vehicle2"
                            name="vehicle2"
                            value="Car"
                            class="input-checkbox"
                          />
                          <label for="vehicle2">Vai trò Quản lý chuỗi</label>
                        </div>
                      </div>
                    </div>
                    <div class="field">
                      <div class="label">
                        <span>Trạng thái</span>
                        <span class="required">(*)</span>
                      </div>
                      <div class="checkbox">
                        <div class="input small">
                          <input value="chính thức" />
                        </div>
                        <div
                          class="checkbox-item"
                          style="    margin-left: 12px;"
                        >
                          <input
                            type="checkbox"
                            id="vehicle2"
                            name="vehicle2"
                            value="Car"
                            class="input-checkbox"
                          />
                          <label for="vehicle2"
                            >Cho phép làm việc với phần mềm CUKCUK</label
                          >
                        </div>
                      </div>
                    </div>
                    <div class="field">
                      <div class="label"></div>
                      <div
                        class="checkbox-item"
                        style="display:flex;
    align-items: center;
    width: 18%;"
                      >
                        <input
                          type="checkbox"
                          id="vehicle3"
                          name="vehicle3"
                          value="Bike"
                          class="input-checkbox"
                        />
                        <label style="min-width:100px" for="vehicle3"
                          >Đổi mật khẩu</label
                        >
                      </div>
                    </div>
                  </div>
                  <div class="avt">
                    <img
                      src="https://cdn2.cukcuk.vn/QLNH/resources/Image/ImageNotFound-3x4.png"
                    />

                    <div class="desc">
                      Chỉ được upload file .jpg, .jpeg, .png, .gif.
                    </div>
                  </div>
                </div>

                <v-card-text style="width:100%"> </v-card-text>

                <v-card-actions class="justify-end">
                  <v-btn text @click="dialog.value = false">Close</v-btn>
                </v-card-actions>
              </v-card>
            </template>
          </v-dialog>
        </v-col>
      </v-row>
    </v-app>
    <button @click="dialog = true">click di</button>
  </div>
</template>

<script>
export default {
  props: ["visible"],
  computed: {
    show: {
      get() {
        return this.visible;
      },
      set(value) {
        if (!value) {
          this.$emit("close");
        }
      },
    },
  },
};
</script>
<style>
.sprite {
  background: url("../assets/icon/set-icon.png") no-repeat 0 -2586px;
  width: 16px;
  height: 13px;
}

.sprite {
  background-image: url("/assets/icon/set-icon.png") no-repeat;

  background-position: 0 -2586px;
  width: 16px;
  height: 13px;
}
.modal-action div img {
  height: 20px;
}
.modal-action {
  display: flex;
  padding: 8px;
  height: 40px;
}
.modal-action div {
  display: flex;
  margin-left: 8px;
  padding: 0 4px;
}
.modal-action div p {
  margin-top: 3px;
}
.modal-action div span {
  padding-left: 8px;
}
.modal-action :hover {
  background: #fff;
  /* border: 1px solid blue; */
}
div .row {
  margin: 0;
}
#form input {
  border-style: inset;
  width: 100%;
}
.col {
  padding: 4px !important;
}

.form-container {
  display: flex;
  justify-content: flex-between;
  align-items: flex-start;
}

.avt {
  padding-top: 12px;
}

.avt img {
  width: 120px;
  height: 120px;
}

.form {
  padding: 12px;
  width: 100%;
}
.field {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin-bottom: 8px;
}
.field .label {
  width: 60%;
  max-width: 140px;
  min-width: 100px;
  text-align: left;
  white-space: nowrap;
}
.field input {
  background-color: #f2f2f2;
  color: #000;
  padding: 3px 5px 3px !important;
  font: 12px/15px TahomaCustom, arial, sans-serif !important;
  line-height: 22px;
  width: 100%;
}
.required {
  color: red;
}
.input.small {
  width: 40%;
}
.input.medium {
  width: 60%;
}
.input.large {
  width: 100%;
}

.field .checkbox {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
}
label {
  margin: 0px;
}
.field .checkbox .checkbox-item {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin-right: 12px;
}

.field .checkbox .checkbox-item .input-checkbox {
  width: 13px;
  margin-right: 12px;
}
.field .checkbox .checkbox-item .label {
  white-space: nowrap;
}

.field .warning {
  font-size: 11px;
}

.field-group {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.groupLeft {
  width: 60%;
}
.groupRight {
  width: calc(40% - 5px);
  margin-left: 5px;
}

.groupRight .field .label {
  text-align: center;
}
</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
