<template>
  <div>
    <h1>Branding</h1>
    <VContainer fluid>
      <VRow>
        <VCol cols="2">
          <VBtn
            class="mb-5"
            block
            @click="showPC"
          >
            Primary Color
          </VBtn>
          <VColorPicker
            v-if="isShowPc"
            v-model="firstColor"
            style="width: 100%;"
            class="mb-5"
          />
          <VBtn
            class="mb-5"
            block
            @click="showBC"
          >
            BackGround Color
          </VBtn>
          <VColorPicker
            v-if="isShowBc"
            v-model="backGroundColor"
            style="width: 100%;"
            class="mb-5"
          />
          <VBtn
            class="mb-5"
            block
            @click="showCC"
          >
            Content Color
          </VBtn>
          <VColorPicker
            v-if="isShowCc"
            v-model="contextColor"
            style="width: 100%;"
            class="mb-5"
          />
        </VCol>
        <VCol cols="10">
          <h1 v-if="firstColor">
            Primary Color : {{ firstColor }}
          </h1>
          <h1 v-if="backGroundColor">
            Background Color : {{ backGroundColor }}
          </h1>
          <h1 v-if="contextColor">
            Content Color : {{ contextColor }}
          </h1>
        </VCol>
      </VRow>
    </VContainer>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/component-api-style
  data() {
    return {

      firstColor: null,
      backGroundColor: null, 
      contextColor: null,
      isShowPc: false,
      isShowBc: false,
      isShowCc: false,
    }
  },
  // eslint-disable-next-line vue/component-api-style
  methods: {
    showPC(){
      if(!this.isShowPc){
        this.isShowPc = true
        this.isShowBc = false
        this.isShowCc = false
      }else{
        this.isShowPc = false
      }
    },
    showBC(){
      if(!this.isShowBc){
        this.isShowPc = false
        this.isShowBc = true
        this.isShowCc = false
      }else{
        this.isShowBc = false
      }
    },
    showCC(){
      if(!this.isShowCc){
        this.isShowPc = false
        this.isShowBc = false
        this.isShowCc = true
      }else{
        this.isShowCc = false
      }
    },
  },
}
</script>
