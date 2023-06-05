<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <h1>吉他社</h1>
      </v-col>
      <v-col cols="12">
        <v-tabs align-tabs="center" color="yellow" grow v-model="selectedTab">
          <v-tab v-for="(tab, i) in tabs" :key="tab" :value="i">{{ tab }}</v-tab>
        </v-tabs>
        <v-window v-model="selectedTab">
          <v-window-item :value="0">
            <v-table>
              <thead class="">
                <tr>
                  <th>日期</th>
                  <th>名稱</th>
                  <th>地點</th>
                  <th>主持人</th>
                  <th>說明</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="event in events" :key="event.date">
                  <td>{{ event.date }}</td>
                  <td>{{ event.name }}</td>
                  <td>{{ event.place }}</td>
                  <td>{{ event.host }}</td>
                  <td>
                    <pre>
                       {{ event.description }}
                      </pre>
                  </td>
                </tr>
              </tbody>
            </v-table>
          </v-window-item>
          <v-window-item :value="1">
            <v-expansion-panels>
              <v-expansion-panel>
                <v-expansion-panel-title>吉他社社史</v-expansion-panel-title>
                <v-expansion-panel-text>
                  本社成立於76年7月15日，迄今五年有餘，<br>
                  初為一群愛好吉他的同學的聚會，後由王小明提議成立吉他社，<br>
                  起初成立時，也遭遇些許困難，但在眾多愛好吉他的同學共同努力下，<br>
                  終於成立吉他社，提供吉他愛好者一個相互交流的園地，<br>
                  王小明並被推舉為第一屆社長。<br>
                  五年多來參加多次全國性比賽，履有佳績，並與其他學校的吉他社皆有密切交流，<br>
                  在校內外不定時舉行吉他音樂會，皆有不錯的評價。<br>
                  未來，在吉他教學上，將朝多元化教學模式發展，並建立吉他社網站，<br>
                  提供更多吉他的教學，讓對吉他有興趣的朋友們，有一個更好的學習園地。
                </v-expansion-panel-text>
              </v-expansion-panel>
              <v-expansion-panel>
                <v-expansion-panel-title>社長資料</v-expansion-panel-title>
                <v-expansion-panel-text>
                  姓名：王小明<br>
                  出生年月日：民國73年10月8日生<br>
                  身高：172公分<br>
                  體重：60公斤<br>
                  星座：天秤座<br>
                  興趣：詩詞，音樂(特別是吉他)<br>
                  經歷：多次參予吉他演奏比賽(民歌比賽)多獲好評
                </v-expansion-panel-text>
              </v-expansion-panel>
              <v-expansion-panel>
                <v-expansion-panel-title>指導老師資料</v-expansion-panel-title>
                <v-expansion-panel-text>
                  姓名：陳小英<br>
                  出生年月日：民國57年10月22日<br>
                  身高：168公分<br>
                  體重：50公斤<br>
                  興趣：古典吉他<br>
                  經歷：民歌餐廳駐唱歌手7年、詞曲創作、吉他教學5年。
                </v-expansion-panel-text>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-window-item>
          <v-window-item :value="2">
            <v-list>
              <v-list-item v-for="l in learning" :key="l">{{ l }}</v-list-item>
            </v-list>
          </v-window-item>
        </v-window>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue'

const selectedTab = ref(0)
const tabs = [
  '活動公告',
  '社史',
  '教學內容'
]
const events = [
  {
    date: '9/16',
    name: '社員大會',
    place: '吉他社教室',
    host: '王小明',
    description: `
      1.入社歡迎茶會
      2.指導老師致詞
      3.社長致詞
      4.社規介紹以及教學內容之簡介
    `
  },
  {
    date: '10/31',
    name: '校內吉他表演',
    place: '學校大禮堂',
    host: '王小明社長',
    description: `
      以吉他演奏演唱民歌，曲目如下
      1.海浬來的沙
      2.微風往事
      3.七月涼山
      4.明天會更好(大合唱)
    `
  }
]
const learning = [
  '基礎樂理',
  '常用之吉他技巧',
  '音程介紹以及音程表內容',
  '節奏型態',
  '和絃及級數和絃',
  '和絃公式',
  '轉位複合',
  '調音法',
  '吉他的保養',
  '如何轉調'
]
</script>

<style scoped>
:deep(th) {
  color: #fff !important;
}
</style>
