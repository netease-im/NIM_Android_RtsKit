# RtsKit 使用说明

## 全局配置项 RTSOptions

RtsKit 组件提供了全局配置类 RTSOptions，初始化 RtsKit 时传入 RTSOptions 对象。

| 类型   | AVChatOptions 属性        | 说明         |
| ---- | ----------------------- | ---------- |
| void | logout(Context context) | 被踢出时，调用的方法 |

## 初始化

在应用的 Application 的 **主进程** 中初始化 RtsKit。

```
RTSOptions rtsOptions = new RTSOptions() {
	@Override
	public void logout(Context context) {
		// 主程序登出操作
	}
};
// 初始化 RtsKit
RTSKit.init(rtsOptions);
// 初始化 Rts 中的其他配置项（可选）
RTSHelper.init();
```

RtsKit 中用到的 Activity 已经在RtsKit 工程的 AndroidManifest.xml 文件中注册好，上层 APP 无需再去添加注册。

## 快速使用

### 发起 RTS 呼叫

- API 原型

```
/**
 * 发起 rts 呼叫
 * @param context 上下文
 * @param account 被叫方账号
 */
public static void startRTSSession(Context context, String account) 
```

- 参数介绍

| 参数      | 说明    |
| ------- | ----- |
| context | 上下文   |
| account | 被叫方账号 |

- 示例

```
RTSKit.startRTSSession(context, account);
```

### 接听 RTS 呼叫

接听 RTS 呼叫已经封装在 RtsKit 中，不需要用户做任何操作，初始化 RtsKit 即可。
