<template>
  <div class="Font">
    <div class="test">
      <template>
        <div
          v-for="(fontFamily, index) in fontFamilyList"
          :class="['box']"
          ref="fontFamiyRef"
          :key="index"
          :style="{'font-family': fontFamily.name}">
          <p>{{ dummyText }}</p>
          <h2 :class="[{gray: fontFamily.fontType === FONT_TYPE.NOT_FOUND}]">{{ fontFamily.label }}</h2>
          <h3>{{fontFamily.fontType === FONT_TYPE.NOT_FOUND ? '☓' : '○'}}</h3>
        </div>
      </template>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import { detectFont } from 'detect-font';

const dummyText = 'あのイーハトーヴォのすきとおった風、夏でも底に冷たさをもつ青いそら、うつくしい森で飾られたモリーオ市、郊外のぎらぎらひかる草の波。'

const FONT_TYPE = {
  NOT_DETECT: 'NOT_DETECT',
  DETECTED: 'DETECTED',
  NOT_FOUND: 'NOT_FOUND',
}

export default Vue.extend({
  name: 'Font', 
  data() {
    return {
        dummyText,
        fontFamilyList: [
          {
            name: 'sans-serif',
            label: 'sans-serif',
            fontType: FONT_TYPE.NOT_DETECT
            
          },
          {
            name: 'serif',
            label: 'serif',
            fontType: FONT_TYPE.NOT_DETECT
            
          },
          {
            name: "Meiryo",
            label: "'Meiryo' '英語指定'",
            fontType: FONT_TYPE.NOT_DETECT
            
          },
          {
            name: '"メイリオ"',
            label: '"メイリオ" "日本語指定"',
            fontType: FONT_TYPE.NOT_DETECT
            
          },
          {
            name: "'Hiragino Kaku Gothic ProN'",
            label: "'Hiragino Kaku Gothic ProN' '英語指定'",
            fontType: FONT_TYPE.NOT_DETECT
            
          },
          {
            name: "'ヒラギノ角ゴ ProN W3'",
            label: "'ヒラギノ角ゴ ProN W3' '日本語指定'",
            fontType: FONT_TYPE.NOT_DETECT
            
          },
          {
            name: '"メイリオ","Hiragino Kaku Gothic ProN",Meiryo,"ヒラギノ角ゴ Pro W3","MS PGothic","MS UI Gothic",Helvetica,Arial,sans-serif',
            label: '"メイリオ","Hiragino Kaku Gothic ProN",Meiryo,"ヒラギノ角ゴ Pro W3","MS PGothic","MS UI Gothic",Helvetica,Arial,sans-serif 入り乱れたもの',
            fontType: FONT_TYPE.NOT_DETECT
          },
        ]
      }
  },
  computed: {
    FONT_TYPE() {
      return FONT_TYPE
    }
  },
  mounted() {
    console.log(this.$refs.fontFamiyRef)
    const arr: any = this.$refs.fontFamiyRef
    arr.forEach((element: Element, index: number) => {
      const detectedFont = detectFont(element)
      console.log(detectedFont)
      this.fontFamilyList[index].label = detectedFont || this.fontFamilyList[index].label
      this.fontFamilyList[index].fontType = detectedFont ? FONT_TYPE.DETECTED : FONT_TYPE.NOT_FOUND
    })
    
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.test {
  display: flex;
  flex-direction: column;
}
.box {
  padding: 10px;
  font-size: 30px;
  border: solid 2px black;
}
.gray {
  background: #d4d4d4;
}
h2 {
  font-size: 20px;
}
p {
  width: 80%;
  box-sizing: border-box;
}
</style>
