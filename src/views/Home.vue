<template>
  <div>
    <b-container>
      <b-row>
        <b-col cols="4" v-for="index in orderData" :key="index">
          <User
            :image="index.image"
            :name="index.name"
            :price="index.price"
            :tag="index.tag"
            @updateOrder="sub"
          />
          <b-modal id="bv-modal-example" hide-footer>
            <template #modal-title class="text-center">แจ้งเตือน</template>
            <div class="d-block text-center">
              <p>หยิบสินค้าเรียบร้อย</p>
            </div>
            <b-button
              class="mt-3"
              block
              @click="$bvModal.hide('bv-modal-example')"
              >ปิด</b-button
            >
          </b-modal>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
import User from "@/components/user.vue";
export default {
  name: "Home",
  props: {
    orderData: Array,
  },
  components: {
    User,
  },
  data() {
    return {};
  },
  methods: {
    sub(value) {
      this.$emit("updateOrder", value);
    },
  },
};
</script>
