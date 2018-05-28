﻿# 德州扑克AI算法
该德州扑克AI算法是为了参加趋势科技德州扑克比赛而设计的。该算法部分参考`Mick West`的[资料](https://www.zybuluo.com/mdeditor)。算法特点是自己根据明牌的情况去推算自己赢得这场的概率,赔率,回报率。最终得到危险系数(`risk rate`),根据`risk rate`的阀值做出`action`
> * 赢率 = 赢的次数/总模拟数
> * 赔率 = 自己已下的注/池底
> * 回报率 = 赢率/赔率
> * 危险系数 = f(回报率)
## 待办事项
- [x] 连接服务器
- [x] 计算赢率
- [x] 计算赔率
- [x] 计算回报率
- [x] 计算危险系数
- [x] 根据危险系数做出行动
- [x] 同步场上信息

## 如何去计算赢率
除去公共牌和自己手里的牌，再从牌堆里随机发派到场上还存活的玩家。当场上的公共牌不足5张时，应从牌堆里补够5张。然后去计算每个玩家能组成的最大牌力。在一次模拟局中，如果自己的牌力大于其他玩家的牌力，那么算自己赢的这场比赛`count++`。如果自己模拟1000次，那么`赢率=count/1000`。模拟次数应根据计算机计算能力而调整。