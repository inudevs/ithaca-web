<script>
export default {
  data() {
    return {
      requests: [
        {
          chat: '준호야, 1을 여기에 더하면 반올림이 되는 거야!',
          message: '쌤~ 이건 아무리 봐도 모르겠어요...!',
          timestamp: 1564933932,
          sender: 'mentee',
          mentor: {
            name: '송지호',
            grade: 1,
            klass: 5,
            number: 15,
          },
          mentee: {
            name: '여준호',
            grade: 1,
            klass: 5,
            number: 20,
          },
        },
        {
          chat: '준호야, 1을 여기에 더하면 반올림이 되는 거야!',
          message: '쌤~ 이건 아무리 봐도 모르겠어요...!',
          timestamp: 1564933932,
          sender: 'mentee',
          mentor: {
            name: '송지호',
            grade: 1,
            klass: 5,
            number: 15,
          },
          mentee: {
            name: '여준호',
            grade: 1,
            klass: 5,
            number: 20,
          },
        },
        {
          chat: '준호야, 1을 여기에 더하면 반올림이 되는 거야!',
          message: '쌤~ 이건 아무리 봐도 모르겠어요...!',
          timestamp: 1564933932,
          sender: 'mentee',
          mentor: {
            name: '송지호',
            grade: 1,
            klass: 5,
            number: 15,
          },
          mentee: {
            name: '여준호',
            grade: 1,
            klass: 5,
            number: 20,
          },
        },
      ],
      hide: [],
    };
  },
  created() {
    this.hide = Array(this.requests.length).fill(0);
  },
  methods: {
    getUserSerial(user) {
      return `${user.grade}학년 ${user.klass}반`;
    },
    onClickOpen(idx) {
      this.$set(this.hide, idx, !this.hide[idx]);
    },
  },
};
</script>

<template>
  <div class="page">
    <div class="page__requests">
      <div
        class="request"
        v-for="(item, idx) in requests"
        :key="idx"
      >
        <div class="request__content">
          <div class="request__message">
            <i
              class="fas fa-angle-down"
              @click="onClickOpen(idx - 1)"
            />
            {{ item.message }}
          </div>
          <div
            class="request__chat"
            v-if="hide[idx - 1]"
          >
            {{ item.chat }}
          </div>
          <div class="request__meta">
            <div class="request__users">
              <div class="request__mentor">
                <span class="request__badge">
                  멘토
                </span>
                <span class="request__mentor-serial">
                  {{ getUserSerial(item.mentor) }}
                </span>
                <span class="request__mentor-name">
                  {{ item.mentor.name }}
                </span>
              </div>
              <div class="request__mentee">
                <span class="request__badge">
                  멘티
                </span>
                <span class="request__mentee-serial">
                  {{ getUserSerial(item.mentee) }}
                </span>
                <span class="request__mentee-name">
                  {{ item.mentee.name }}
                </span>
              </div>
            </div>
            <div class="request__timestamp">
              {{ item.timestamp }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.page {
  width: 100%;

  &__requests {
    margin-top: 2rem;
    width: 100%;
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
}

.request {
  margin: auto;
  padding: 1rem;
  background-color: #e9ecef;
  margin-bottom: 0.7rem;
  border-radius: 10px;
  display: flex;
  flex-direction: row;
  width: 80%;

  &__content {
    width: 100%;
  }

  &__message {
    font-size: 1.5rem;
    font-family: bold;
  }

  &__meta {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  &__users {
    display: flex;
    flex-direction: column;
  }

  &__mentor {
    margin-top: 0.2rem;
    margin-bottom: 0.2rem;
  }

  &__badge {
    font-size: 0.9rem;
    color: white;
    background-color: #495057;
    border-radius: 5px;
    padding: 2px;
    display: inline-flex;
    justify-content: center;
    align-content: center;
  }

  &__timestamp {
    align-self: flex-end;
  }
}
</style>
