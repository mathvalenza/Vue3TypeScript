<template>
  <div class="add">
        <h3>Addition Calculator</h3>
        <form id="sumComp">
            <input class="form-control" v-model="num1">
            <input class="form-control" v-model="num2">
            <button @click="addNumbers" type="button" class="btn btn-light">
            Add me!
        </button>
        </form>
        <p><strong>Sum:</strong> {{ sum }}</p>
    </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const num1 = ref(0); // ref() makes it reactive. If we don't do this, v-model has no effect
    const num2 = ref(0);
    const sum = ref('some string'); // we can initialize it as a String.
    // ref() makes it reactive. If we don't do this, event if sum is changed in script, it has no effect in template

    function addNumbers() {
      console.log(num1); // { value: TYPED_VALUE, __v_isRef: true }
      console.log(num2);
      sum.value = +num1.value + +num2.value;
    }

    return {
      num1,
      num2,
      sum,
      addNumbers,
    }
  },
});
</script>

<style scoped>
    .add {
        background: #d67182;
        box-shadow: 1px 3px 6px #a3a3a3;
        padding: 50px 30px;
        width: 300px;
        text-align: center;
        margin: 80px auto;
    }
    p, h3 {
        color: #FFFFFF;
    }
    #sum {
        margin-top: 25px;
    }
    .form-control {
        margin-bottom: 15px;
    }
    .btn {
        margin-bottom: 30px;
    }
</style>
