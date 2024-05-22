非正式SDK  示例Demo
目前有登录（Google）  支付（Google） 广告（Applovin，Admob聚合） 数据上报广告归因（Adjustt） 
SDK目前调用接口方法名：
广告:
广告形式为聚合广告   至于使用什么样的广告  则需要在hi_game_config.json里面配置参数和class路径 
HiGameSDK.getinstance.showBanner()  展示banner
HiGameSDK.getInstance().closeBanner()  关闭banner
插屏和激励视频
HiGameSDK.getInstance().showInterstitial()
HiGameSDK.getInstance().showRewardVideo()

//多渠道登录
 HiGameSDK.getInstance().Login(this)  //目前只实现了Google登录  其他登录方式待集成实现  只需要调用Login方法即可实现登录

 //Google支付
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
     // 自定义上报
    fun onCustomEvent(eventName: String?, eventData: HashMap<String?, Any?>?) {
        // 直接调用 HiGameSDK 的 onCustomEvent 方法，并传入方法参数中的 eventName 和 eventData
        HiGameSDK.getInstance().onCustomEvent(eventName, eventData)
    }
    //完成新手教程的时候 执行
    fun onCompleteTutorial(tutorialID: Int, content: String?) {
        HiGameSDK.getInstance().onCompleteTutorial(tutorialID, content)
    }
    //升级
    fun onLevelup(role: HiRoleData?) {
        HiGameSDK.getInstance().onLevelup(role)
    }
    //自定义事件， 进入游戏成功
    fun onEnterGame(role: HiRoleData?) {
        HiGameSDK.getInstance().onEnterGame(role)
    }
    // 自定义事件， 创建角色成功
    fun onCreateRole(role: HiRoleData?) {
        HiGameSDK.getInstance().onCreateRole(role)
    }
    /**
     * 购买成功的时候，调用
     * af_purchase
     * price: 分为单位
     */
    fun onPurchase(order: HiOrder?) {
        HiGameSDK.getInstance().onPurchase(order)
    }
    /**
     * 自定义事件， 开始购买（SDK下单成功）
     * price：分为单位
     */
    fun onPurchaseBegin(order: HiOrder?) {
        HiGameSDK.getInstance().onPurchaseBegin(order)
    }

    /**
     * 注册成功的时候 上报
     * af_complete_registration
     */
    fun onCompleteRegistration(regType: Int) {
        HiGameSDK.getInstance().onCompleteRegistration(regType)
    }
    /**
     * 登陆成功的时候 上报
     * af_login
     */
    fun onLogin() {
        HiGameSDK.getInstance().onLogin()
    }

    /**
     * 自定义事件： SDK初始化开始
     */
    fun onInitStart() {
        HiGameSDK.getInstance().onInitStart()
    }

    /**
     * 自定义事件： SDK初始化完成
     */
    fun onInitFinish() {
        HiGameSDK.getInstance().onInitFinish()
    }

    /**
     * 自定义事件： SDK登陆开始
     */
    fun onLoginStart() {
        HiGameSDK.getInstance().onLoginStart()
    }

    其他功能待开发中
