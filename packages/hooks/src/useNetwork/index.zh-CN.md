---
title: useNetwork
nav:
  title: Hooks
  path: /hooks
group:
  title: State
  path: /state
  order: 12
legacy: /state/use-network
---

# useNetwork

优雅地返回 NetworkInformation 对象，其中包含有关系统连接的信息

## 代码演示

### Default usage

<code src="./demo/demo1.tsx" />

## API

```javascript
interface INetworkState {
  rtt?: number;
  since?: Date;
  type?: string;
  online?: boolean;
  downlink?: number;
  saveData?: boolean;
  downlinkMax?: number;
  effectiveType?: string;
}

const result: INetworkState = useNetwork(
  defaultValue?: INetworkState | (() => INetworkState),
);
```

### 参数

| Property | Description                                 | Type                   | Default |
|---------|----------------------------------------------|------------------------|--------|
| defaultValue | Optional，set a default networkState value  | INetworkState \| () => INetworkState | {} |

### 结果（INetworkState）

| 属性 | 描述                                         | 类型                 |
|----------|--------------------------------------|----------------------|
| rtt  | 当前连接下评估的往返时延 | number |
| type  | 设备使用与所述网络进行通信的连接的类型 | 'bluetooth' \| 'cellular' \| 'ethernet' \| 'none' \| 'wifi' \| 'wimax' \| 'other' \| 'unknown' |
| online  | 网络是否为在线 | boolean |
| since  | 在线与不在线最后改变时间 | Date |
| downlink  | 有效带宽估算（单位：兆比特/秒） | number |
| downlinkMax  | 最大下行速度（单位：兆比特/秒） | number |
| saveData  | 用户代理是否设置了减少数据使用的选项 | boolean  |
| effectiveType  | 网络连接的类型 | 'slow-2g' \| '2g' \| '3g' \| '4g'  |

