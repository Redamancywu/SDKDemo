# SDK Demo

## 介绍

目前示例 Demo 包含以下功能模块：

- 登录（Google）
- 支付（Google）
- 广告（Applovin，Admob聚合）
- 数据上报广告归因（Adjust）

## 广告接口

广告形式为聚合广告，使用的广告类型需要在 `hi_game_config.json` 中配置参数和 class 路径。

### 展示 Banner 广告

HiGameSDK.getInstance().showBanner()

HiGameSDK.getInstance().closeBanner()  关闭banner
### 插屏和激励视频

HiGameSDK.getInstance().showInterstitial()
HiGameSDK.getInstance().showRewardVideo()

### 多渠道登录
 HiGameSDK.getInstance().Login(this)  //目前只实现了Google登录  其他登录方式待集成实现  只需要调用Login方法即可实现登录
 
### 支付
 HiGameSDK.getInstance().Pay(this,payParams,object :IPayCallBack{
            override fun onPaySuccess(orderId: String?) {
                TODO("Not yet implemented")
            }
            override fun onPayFailure(orderId: String?, errorCode: Int, errorMessage: String?) {
                TODO("Not yet implemented")
            }
            override fun onPayCanceled(orderId: String?) {
                TODO("Not yet implemented")
            }
 })
 
### 自定义上报
    fun onCustomEvent(eventName: String?, eventData: HashMap<String?, Any?>?) {
        // 直接调用 HiGameSDK 的 onCustomEvent 方法，并传入方法参数中的 eventName 和 eventData
        HiGameSDK.getInstance().onCustomEvent(eventName, eventData)
    }
### 完成新手教程的时候 执行
    fun onCompleteTutorial(tutorialID: Int, content: String?) {
        HiGameSDK.getInstance().onCompleteTutorial(tutorialID, content)
    }
### 升级
    fun onLevelup(role: HiRoleData?) {
        HiGameSDK.getInstance().onLevelup(role)
    }
### 自定义事件， 进入游戏成功
    fun onEnterGame(role: HiRoleData?) {
        HiGameSDK.getInstance().onEnterGame(role)
    }
###  自定义事件， 创建角色成功
    fun onCreateRole(role: HiRoleData?) {
        HiGameSDK.getInstance().onCreateRole(role)
    }
 ### 购买成功    
    /**
     * 购买成功的时候，调用
     * af_purchase
     * price: 分为单位
     */

    fun onPurchase(order: HiOrder?) {
        HiGameSDK.getInstance().onPurchase(order)
    }
 ### 开始购买
    /**
     * 自定义事件， 开始购买（SDK下单成功）
     * price：分为单位
     */
    fun onPurchaseBegin(order: HiOrder?) {
        HiGameSDK.getInstance().onPurchaseBegin(order)
    }
 ### 注册成功
    /**
     * 注册成功的时候 上报
     * af_complete_registration
     */
    fun onCompleteRegistration(regType: Int) {
        HiGameSDK.getInstance().onCompleteRegistration(regType)
    }
### 登录成功
    /**
     * 登陆成功的时候 上报
     * af_login
     */
    fun onLogin() {
        HiGameSDK.getInstance().onLogin()
    }
 ### SDK初始化开始
    /**
     * 自定义事件： SDK初始化开始
     */
    fun onInitStart() {
        HiGameSDK.getInstance().onInitStart()
    }
 ### SDK初始话成功
    /**
     * 自定义事件： SDK初始化完成
     */
    fun onInitFinish() {
        HiGameSDK.getInstance().onInitFinish()
    }
 ### SDK登录开始
    /**
     * 自定义事件： SDK登陆开始
     */
    fun onLoginStart() {
        HiGameSDK.getInstance().onLoginStart()
    }


### 解释

- **介绍部分**：简要描述了当前 Demo 包含的功能模块。
- **广告接口**：详细说明了广告相关的接口，包括展示和关闭广告的方法。
- **登录接口**：介绍了当前实现的登录方式，并提供了示例代码。
- **支付接口**：详细描述了 Google 支付的接口和回调方法。
- **数据上报接口**：列出了所有数据上报的方法，并给出了示例代码。
- **其他功能**：提示后续功能的开发计划。

