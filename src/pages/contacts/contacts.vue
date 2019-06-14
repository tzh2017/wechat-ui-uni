<template>
  <view>
    <scroll-view scroll-y="true">
      <!-- 头部 -->
      <view v-for="(item, index) in headers" :key="index">
        <view class="s-list">
          <image class="s-left single-line" :src="item.avatar" mode="aspectFill"></image>
          <view class="s-mid s-name single-line">{{item.name}}</view>
        </view>
        <view class="s-divider"></view>
      </view>

      <view class="s-seper"></view>

      <!-- 联系人 -->
      <view v-for="(item, index) in contacts" :key="index+10">
        <view class="s-list">
          <image class="s-left single-line" :src="item.avatar" mode="aspectFill"></image>
          <view class="s-mid s-name single-line">{{item.name}}</view>
        </view>
        <view class="s-divider"></view>
      </view>
    </scroll-view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          avatar: "/static/logo.png",
          name: "新的朋友",
        },
        {
          avatar: "/static/logo.png",
          name: "群聊",
        },
        {
          avatar: "/static/logo.png",
          name: "标签",
        },
        {
          avatar: "/static/logo.png",
          name: "公众号",
        },
      ],
      contacts: [
        {
          avatar: "/static/avatar/a001.jpg",
          name: "班主任",
        },
        {
          avatar: "/static/avatar/a002.jpg",
          name: "老铁",
        },
        {
          avatar: "/static/avatar/a003.jpg",
          name: "李思思",
        },
        {
          avatar: "/static/avatar/a004.jpg",
          name: "陈赫",
        },
        {
          avatar: "/static/avatar/a005.jpg",
          name: "Faker",
        }
      ]
    };
  },
  onLoad() {
    this.contacts.push(...this.contacts);
    this.contacts.push(...this.contacts);
    this.contacts.push(...this.contacts);
    // let arr = [];
    // arr.push(...this.contacts);
    // arr.push(...this.contacts);
    // arr.push(...this.contacts);
    // this.contacts = arr;
  },
  methods: {}
};
</script>

<style lang="less">
.s-list {
  height: 100upx;
  display: flex;
  align-items: center;

  .s-left {
    width: 64upx;
    height: 64upx;
    margin-left: 32upx;
  }
  .s-mid {
    flex: 1;
    margin: 0 32upx;
    overflow: hidden;
  }

  .s-name {
    font-size: 32upx;
    color: #333333;
  }
}
.s-divider {
  background: #eeeeee;
  height: 1px;
  margin: -1px 0 0 128upx;
  transform: scaleY(0.4);
}

.s-seper{
  background: #eeeeee;
  height: 24upx;
}

.single-line {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
</style>
