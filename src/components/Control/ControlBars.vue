<template>
  <div>
    <el-row>
      <el-col :span="16">
      <el-form-item label="Bars Style" label-width="90px">
        <el-radio-group v-model="bars.type" size="mini">
          <el-radio-button label="simple">Simple</el-radio-button>
          <el-radio-button label="smpte">SMPTE</el-radio-button>
          <el-radio-button label="arib">ARIB</el-radio-button>
          <el-radio-button label="hdr">HDR</el-radio-button>
          <el-radio-button label="sdi">SDI</el-radio-button>
        </el-radio-group>
      </el-form-item>
      </el-col>
      <el-col :span="8" v-if="bars.type=='simple'">
        <el-form-item label="Level" label-width="50px">
          <el-radio-group v-model="bars.level" size="mini">
            <el-radio-button label="75" />
            <el-radio-button label="100" />
            <el-radio-button label="109" />
          </el-radio-group>
        </el-form-item>
      </el-col>
    </el-row>

    <el-row>
      <el-col :span="12">
          <el-form-item label="Overlay Details">
            <el-switch v-model="bars.overlay"></el-switch>
        </el-form-item>
      </el-col>
    </el-row>

  </div>
</template>

<script>
  export default {
    props: {
      modelValue: Object
    },
    computed: {
      bars: {
        get() {
          return this.modelValue // return v-model
        },
        set(value) {
          this.$emit('update:modelValue', value) // update the v-model object to parent component
        }
      },
    }
  }
</script>

<style scoped>
  
</style>
