<template>
  <view>
    <view v-for="(item, index) in sessions" :key="index">
      <view class="s-list">
        <image class="s-left" :src="item.avatar" mode="aspectFill"></image>
        <view class="s-mid">
          <view class="s-name single-line">{{item.name}}</view>
          <view class="s-msg single-line">{{item.msg}}</view>
        </view>
        <view class="s-right">{{item.time}}</view>
      </view>
      <view class="s-divider"></view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      sessions: [
        {
          avatar: "/static/avatar/a001.jpg",
          name: "班主任",
          msg: "你高考考了满分你知道吗？",
          time: "9:00"
        },
        {
          avatar: "/static/avatar/a002.jpg",
          name: "老铁",
          msg: "帮我带饭啊，钱放你桌子上了",
          time: "6:00"
        },
        {
          avatar: "/static/avatar/a003.jpg",
          name: "李思思",
          msg: "你好，你的代码崩了",
          time: "昨天"
        },
        {
          avatar: "/static/avatar/a004.jpg",
          name: "陈赫",
          msg: "打野，上没闪快来",
          time: "昨天"
        },
        {
          avatar: "/static/avatar/a005.jpg",
          name: "Faker",
          msg: "你会玩劫吗？",
          time: "大前天"
        }
      ]
    };
  },
  onLoad() {},
  methods: {}
};
</script>

<style lang="less">
.s-list {
  height: 120upx;
  display: flex;
  align-items: center;

  .s-left {
    width: 80upx;
    height: 80upx;
    margin-left: 32upx;
  }
  .s-mid {
    flex: 1;
    margin: 0 32upx;
    overflow: hidden;
  }
  .s-right {
    height: 100upx;
    color: #dddddd;
    font-size: 24upx;
    margin-right: 32upx;
  }

  .s-name {
    font-size: 32upx;
    color: #333333;
  }

  .s-msg {
    margin-top: 1px;
    font-size: 30upx;
    color: #cccccc;
  }
}
.s-divider {
  background: #eeeeee;
  height: 1px;
  margin: -1px 0 0 144upx;
  transform: scaleY(0.4);
}

.single-line {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
</style>
