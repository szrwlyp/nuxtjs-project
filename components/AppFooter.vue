<script setup lang="ts"></script>

<template>
  <footer class="footer">
    <div class="footer-nav">
      <ul class="nav-ul">
        <li>行业新闻</li>
        <li>企业新闻</li>
        <li>企业活动</li>
      </ul>
      <div class="contact">
        <div class="contact-phone">
          <span class="iconfont icon-phone phone"></span>
          <!-- <img
            src="https://www.chaochuang.com.cn/style/images/icon-phone.png"
            alt=""
          /> -->
          <div>400-070-7770</div>
        </div>
        <span style="margin: 0 16px">|</span>
        <span class="contact-weixin iconfont icon-weixin"></span>
        <!-- <img
          src="https://www.chaochuang.com.cn/style/images/wechat-default.png"
          alt=""
          class="contact-weixin icon-weixin"
        /> -->
      </div>
    </div>
    <div class="copy">
      <ul class="list-unstyled">
        <li>法律声明</li>
        <li>隐私保护</li>
      </ul>
      <span class="center-gap">|</span>
      <div class="copy-text">版权所有 © 2016 南宁超创信息工程有限公司</div>
      <div>ICP 备案号: 桂B2-20030001</div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  background: #f2f2f2;
  font-size: 16px;
  .footer-nav {
    color: #595757;
    padding: 40px 0;
    width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    .nav-ul {
      display: flex;
      font-size: 1.1em;
      align-items: center;
      li {
        padding-right: 50px;
      }
    }
    .contact {
      display: flex;
      align-items: center;
      .contact-phone {
        display: flex;
        align-items: center;
        .phone {
          font-size: 27px;
          margin-right: 4px;
        }
        /* img {
          width: 30px;
          height: 30px;
        } */
      }
      .contact-weixin {
        /* width: 30px;
        height: 30px; */
        font-size: 30px;
      }
    }
  }
  .copy {
    background: #e6e6e6;
    color: #666;
    display: flex;
    padding: 23px;
    justify-content: center;
    font-size: 0.9em;
    .center-gap {
      margin: 0 30px;
    }
    .copy-text {
      margin-right: 20px;
    }
    .list-unstyled {
      display: flex;
      li {
        padding: 0 10px;
      }
    }
  }
}

@media screen and (max-width: 1200px) {
  .footer {
    .footer-nav {
      width: 90%;
    }
  }
}

@media screen and (max-width: 768px) {
  .footer {
    font-size: 15px;
    .footer-nav {
      width: 90%;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 30px 0;
      .contact {
        margin-top: 20px;
      }
    }
    .copy {
      padding: 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
      .center-gap {
        display: none;
      }
      .copy-text {
        margin-top: 10px;
      }
    }
  }
}
</style>
