<script>
import Question from '~/components/Question.vue'

export default {
  components: {
    Question,
  },
  data() {
    return {
      grade: '',
      isCrossDisciplinary: '',
      studyTime: '',
      agreementOptions: [
        '非常同意',
        '比较同意',
        '一般同意',
        '不太同意',
        '非常不同意',
      ],
      frequencyOptions: [
        '经常',
        '有时',
        '较少',
        '很少',
        '从未',
      ],
      timeSpentOptions: [
        '五个半天及以上',
        '四个半天',
        '三个半天',
        '两个半天及以下',
        '无',
      ],
      motivationQuestions: [
        '1. 学习是为了获取奖学金',
        '2. 学习是为了让周围人看得起我',
        '3. 学习是为了提升学术素养',
        '4. 学习是为了文凭',
        '5. 学习是为了满足专业好奇心和兴趣',
      ],
      attitudeQuestions: [
        '6. 我疲于应付各门课程的学习任务',
        '7. 我愿意积极参与课堂讨论',
        '8. 我愿意在学习上投入大量的时间与精力',
        '9. 我愿意主动与老师和同学探讨学习中的问题',
      ],
      environmentQuestions: [
        '10. 学校的学业考核办法给我带来了很大的压力',
        '11. 学校的学业考核办法使我更加地喜欢学习',
        '12. 学校提供的各种学习资源能满足我的学习需求',
        '13. 专业课程教师的教学方式能帮助我有效地学习',
        '14. 导师为我提供了从事课题研究或相关活动的机会',
        '15. 导师能适时地鼓励和表扬我',
        '16. 导师经常组织学生进行交流和研讨',
        '17. 导师经常布置小组活动的研究任务',
      ],
      behaviorQuestions: [
        '18. 与其它专业的同学探讨有关学习的问题',
        '19. 参加跨专业（或领域）的学习活动',
        '20. 参加各种专业学术活动（如学术讲座、学术论坛等）',
        '21. 参加导师的课题（或项目）等研究活动',
        '22. 参与专业实践活动',
        '23. 参与课堂发言或讨论活动',
        '24. 阅读本专业及相关领域的文献',
      ],
      breakQuestions: [
        '25. 我每周的课外学习时间（指看书、查资料、写论文、做作业等）',
        '26. 我每周参加校内外带薪工作时间（如勤工俭学、外出兼职等）',
        '27. 我每周参加校内活动时间（如学生会、社团、志愿者活动等）',
        '28. 我每周参加娱乐、运动、社交等休闲娱活动时间（如逛街、健身、打游戏等）',
      ],
      satisfactionQuestions: [
        '29. 我对自己的学习状况和收获都感到满意',
        '30. 我对导师的学术指导感到满意',
        '31. 我对学校有较好的认同感',
      ],
      gainQuestions: [
        '32. 通过学习，我运用专业知识理解和解决问题的能力提高了',
        '33. 通过学习，我批判性地思考问题的能力提高了',
        '34. 通过学习，我的专业研究能力提高了',
        '35. 通过学习，我的学习兴趣明显增强了',
      ],
    }
  },
}
</script>

<template>
  <div class="survey">
    <h1 class="mb-4 text-3xl font-bold">
      北京工业大学机械类硕士研究生学习投入调查问卷
    </h1>

    <p>
      亲爱的同学：您好！为了更好地了解教育学硕士研究生的学习投入情况，特邀您参与此次
      问卷调查。本问卷采用匿名形式，结果仅作研究之用，请您根据自身情况，做出相应填写。您的真实回答
      将为本研究提供宝贵的依据，在此对您表示衷心的感谢！
    </p>

    <section>
      <h2>一、基本信息</h2>
      <div>
        <label>1.你的年级:</label>
        <select v-model="grade" class="b b-1 b-gray">
          <option value="A">
            研一
          </option>
          <option value="B">
            研二
          </option>
          <option value="C">
            研三
          </option>
        </select>
      </div>

      <div>
        <label>2.你是否为跨专业研究生:</label>
        <select v-model="isCrossDisciplinary" class="b b-1 b-gray">
          <option value="A">
            是
          </option>
          <option value="B">
            否
          </option>
        </select>
      </div>

      <div>
        <label>3.你平均每天用于课外学习的时间是:</label>
        <select v-model="studyTime" class="b b-1 b-gray">
          <option value="A">
            1~2 小时
          </option>
          <option value="B">
            2~4 小时
          </option>
          <option value="C">
            4~6 小时
          </option>
          <option value="D">
            6 小时以上
          </option>
        </select>
      </div>
    </section>

    <section>
      <h2>二、各维度因素</h2>
      <div>
        <Question
          v-for="(question, index) in motivationQuestions"
          :key="index"
          :question="question"
          :options="agreementOptions"
        />
      </div>

      <div>
        <Question
          v-for="(question, index) in attitudeQuestions"
          :key="index"
          :question="question"
          :options="agreementOptions"
        />
      </div>

      <div>
        <Question
          v-for="(question, index) in environmentQuestions"
          :key="index"
          :question="question"
          :options="agreementOptions"
        />
      </div>

      <div>
        <Question
          v-for="(question, index) in behaviorQuestions"
          :key="index"
          :question="question"
          :options="frequencyOptions"
        />
      </div>

      <div>
        <Question
          v-for="(question, index) in breakQuestions"
          :key="index"
          :question="question"
          :options="timeSpentOptions"
        />
      </div>
      <div>
        <Question
          v-for="(question, index) in satisfactionQuestions"
          :key="index"
          :question="question"
          :options="agreementOptions"
        />
      </div>

      <div>
        <Question
          v-for="(question, index) in gainQuestions"
          :key="index"
          :question="question"
          :options="agreementOptions"
        />
      </div>
    </section>
    <!-- 提交按钮 -->
    <div class="flex justify-center">
      <button class="btn-primary btn" onclick="alert('已提交')">
        提交
      </button>
    </div>
  </div>
</template>

<style>
.survey {
  text-align: left;
  max-width: 700px;
  margin: 20px auto;
}
.survey h1,
.survey h2,
.survey h3 {
  color: #333;
}
.survey div {
  margin-bottom: 15px;
}
</style>
