<!-- eslint-disable vue/require-v-for-key -->
<template>
  <div class="m-a flex flex-col">
    <div id="erx-wrapper" class="w-xl m-a text-black select-none" style="font-family: Noto Serif SC;">
      <div id="erx-print-area" class="bg-white b-1 b-black b-solid p-8">
        <div id="title" contenteditable class="my-4 text-5 font-600 text-center">
          <span class="mr-16 text-5 font-600">上海市精神卫生中心</span>处方笺
        </div>
        <div id="patient-form" class="flex flex-col">
          <div class="my-2 flex justify-between">
            <p class="mr-4">
              <span class="mr-2">
                姓名:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="5" />
                <span contenteditable>张三花</span>
                <UnderLine len="12" />
              </span>
            </p>
            <p class="mr-4">
              <span class="mr-2">
                性别:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="5" />
                <span contenteditable>女</span>
                <UnderLine len="6" />
              </span>
            </p>
            <p>
              <span class="mr-2">
                年龄:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="6" />
                <span contenteditable>29</span> 岁
                <UnderLine len="12" />
              </span>
            </p>
          </div>
          <div class="my-2 flex">
            <p>
              <span class="mr-2">
                联系电话:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="6" />
                <span contenteditable>13554555101</span>
                <UnderLine len="24" />
              </span>
            </p>
          </div>
          <div class="my-2 flex justify-between">
            <div class="flex">
              <span class="mr-8">
                费别:
              </span>
              <div class="flex flex-items-center">
                <span class="mr-2 flex flex-items-center">
                  <div class="select-box">
                    <div class="relative bottom-1 left-1" v-if="insurance === 'insured'">✓</div>
                  </div>
                  <label>医保</label>
                </span>
                <span class="flex flex-items-center">
                  <div class="select-box">
                    <div class="relative bottom-1 left-1" v-if="insurance === 'uninsured'">✓</div>
                  </div>
                  <label>非医保</label>
                </span>
              </div>
            </div>
            <p>
              <span class="mr-2">
                医保/就诊卡号:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable>13554555101</span>
                <UnderLine len="24" />
              </span>
            </p>
          </div>
          <div class="my-2 flex justify-between">
            <p>
              <span class="mr-2">
                门诊/住院病历号:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable>162348</span>
                <UnderLine len="10" />
              </span>
            </p>
            <p>
              <span class="mr-2">
                科别/病区-床位号:
              </span>
              <span class="underline underline-offset-8">
                <span contenteditable>特需（精神2）</span>
                <UnderLine len="12" />
              </span>
            </p>
          </div>
          <div class="my-2 flex">
            <p>
              <span class="mr-2">
                临床诊断:
              </span>
              <span class="underline underline-offset-8">
                <span contenteditable>F64.000:F31.301</span>
                <UnderLine len="12" />
              </span>
            </p>
          </div>
          <div class="my-2 flex justify-between">
            <p>
              <span class="mr-2">
                皮试结果:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable> </span>
                <UnderLine len="28" />
              </span>
            </p>
            <p>
              <span class="mr-2">
                开具日期:
              </span>
              <span class="mr-2 underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable>2024</span>
                <UnderLine len="6" />
              </span>年
              <span class="mr-2 underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable>01</span>
                <UnderLine len="4" />
              </span>月
              <span class="mr-2 underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable>01</span>
                <UnderLine len="4" />
              </span>日
            </p>
          </div>
        </div>
        <p class="my-4 text-6 font-500">Rp</p>
        <div id="rx" class="min-h-xs w-full flex flex-col">
          <!-- vue list render recordArr in grid layout -->
          <div v-for="item in recordArr" class="flex flex-col justify-between">
            <div class="flex justify-between my-4">
              <div contenteditable>{{ item.drug }}</div>
              <div contenteditable>{{ item.spec }}</div>
              <div contenteditable>{{ item.amount }}</div>
            </div>
            <div class="flex justify-between mb-4">
              <div>Sig</div>
              <div contenteditable>{{ item.method }}</div>
              <div contenteditable>{{ item.freq }}</div>
              <div contenteditable>{{ item.time }}</div>
            </div>
          </div>
          <div class="w-full h-1px bg-black" />
          <p class="mb-8">以下空白，修改无效</p>
        </div>
        <div id="doctor-form" class="flex justify-between">
          <p>
            <span class="mr-2">
              审核:
            </span>
            <span class="underline underline-offset-8">
              <UnderLine len="1" />
              <span contenteditable> </span>
              <UnderLine len="24" />
            </span>
          </p>
          <div class="flex">
            <p>
              <span class="mr-2">
                调配:
              </span>
              <span class="mr-2 underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable> </span>
                <UnderLine len="24" />
              </span>
            </p>
            <p>
              <span class="mr-2">
                医师:
              </span>
              <span class="underline underline-offset-8">
                <UnderLine len="1" />
                <span contenteditable> </span>
                <UnderLine len="24" />
              </span>
            </p>
          </div>
        </div>
        <div id="doctor-form" class="my-1 flex justify-between">
          <p>
            <span class="mr-2">
              核对发药:
            </span>
            <span class="underline underline-offset-8">
              <UnderLine len="1" />
              <span contenteditable> </span>
              <UnderLine len="56" />
            </span>
          </p>
          <p>
            <span class="mr-2">
              药品金额:
            </span>
            <span class="mr-2 underline underline-offset-8">
              <UnderLine len="2" />
              <span contenteditable>355.15</span>
              <UnderLine len="8" />
            </span>
          </p>
        </div>
      </div>
    </div>
    <div class="my-4 w-xl mx-a flex justify-around flex-items-center">
      <fieldset @change="setInsurance">
        <legend>费别:</legend>
        <div class="flex justify-around">
          <div class="mx-4">
            <input type="radio" id="insured" name="insurance" value="insured" checked />
            <label for="insured">医保</label>
          </div>
          <div class="mx-4">
            <input type="radio" id="uninsured" name="insurance" value="uninsured" />
            <label for="uninsured">非医保</label>
          </div>
        </div>
      </fieldset>
      <div>
        <button class="mx-4" @click="addRecord">增加条目</button>
        <button class="mx-4" @click="exportRx">导出</button>
      </div>
    </div>
  </div>
</template>

<style>
.select-box {
  border: 1px solid #000;
  border-radius: 2px;
  height: 1rem;
  width: 1rem;
  margin-right: 0.1rem;
}
</style>

<script setup lang="ts">
import { toJpeg } from 'html-to-image';
import UnderLine from './UnderLine.vue';
import { ref } from 'vue';

const defaultRec = {
  drug: "富马酸喹硫平片",
  spec: "200mg*20片/盒",
  amount: "30片",
  method: "口服",
  freq: "1片/次",
  time: "每天晚上"
}

const insurance = ref("insured")
const recordArr = ref([defaultRec])

const setInsurance = (e: any) => {
  insurance.value = e.target.value
}

const addRecord = () => {
  recordArr.value.push(defaultRec)
}

const exportRx = () => {
  // @ts-ignore
  toJpeg(document.getElementById('erx-print-area'), { quality: 0.95, backgroundColor: "white" })
    .then(function (dataUrl) {
      var link = document.createElement('a');
      link.download = 'eRx.jpg';
      link.href = dataUrl;
      link.click();
    });
}
</script>