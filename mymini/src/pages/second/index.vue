<template>
  <div>
    <button>women</button>
   <i-button bind:click="handleClick">默认按钮</i-button>
<i-button bind:click="handleClick" type="error" long="true">联通两边按钮</i-button>
<i-button bind:click="handleClick" type="primary">Primary</i-button>
<i-button bind:click="handleClick" type="ghost">Ghost</i-button>
<i-button bind:click="handleClick" type="info">Info</i-button>
<i-button bind:click="handleClick" type="success">Success</i-button>
<i-button bind:click="handleClick" type="warning">Warning</i-button>
<i-button bind:click="handleClick" type="error">Error</i-button>
<i-button bind:click="handleClick" type="primary" disabled>禁用按钮</i-button>
<i-grid>
    <i-grid-item i-class="item">
        <i-spin size="small"></i-spin>
    </i-grid-item>
    <i-grid-item i-class="item">
        <i-spin></i-spin>
    </i-grid-item>
    <i-grid-item i-class="item">
        <i-spin size="large"></i-spin>
    </i-grid-item>
</i-grid>
<i-grid>
    <i-grid-item i-class="item">
        <i-spin custom>加载中...</i-spin>
    </i-grid-item>
    <i-grid-item i-class="item">
        <i-spin custom>
            <i-icon type="refresh" size="20" i-class="icon-load"></i-icon>
            <view>Loading</view>
        </i-spin>
    </i-grid-item>
    <i-grid-item i-class="item">
        <i-spin custom>
            <view class="loading"></view>
        </i-spin>
    </i-grid-item>
</i-grid>
  </div>
</template>

<style>
</style>
