<template>
  <div class="card">
    <div class="card-body">
      <div class="row">
        <div class="col-3 img-filed">
          <img class="img-fluid" :src="user.photo" alt="" />
        </div>
        <div class="col-9">
          <div class="username">{{ user.username }}</div>
          <div class="fans">粉丝数：{{ user.followerCount }}</div>
          <button
            @click="follow"
            v-if="!user.is_followed"
            ype="button"
            class="btn btn-danger btn-small"
          >
            +关注
          </button>
          <button
            @click="unfollow"
            v-if="user.is_followed"
            ype="button"
            class="btn btn-danger btn-small"
          >
            已关注
          </button>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "UserProfileInfo",
  props: {
    user: {
      type: Object,
      required: true,
    },
  },
  setup(props, context) {
    const follow = () => {
      context.emit("follow");
    };
    const unfollow = () => {
      context.emit("unfollow");
    };
    return {
      follow,
      unfollow,
    };
  },
};
</script>

<style scoped>
img {
  border-radius: 50%;
}

.username {
  font-weight: bold;
}

.fans {
  font-size: 12px;
  color: gray;
}

button {
  padding: 2px 4px;
  font-size: 13px;
}

.img-field {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>