
# 所谓DCI架构，就是对象的Data数据、对象使用的Context场景、对象的Interactions交互，Data、Context、Interactions 简称DCI。
## Roles

### DCI架构的核心思想是在描述对象的时候，不再强调类或者POJO，而是强调，对象是由Roles来组合组装行为。

## Data

### DCI架构中的数据就是实体对象中的数据。

## Context

### Context掌握了在一个交互场景中角色与一个特定对象实例的关系映射。·

## Interactions

### 交互是作为场景实现的方法，寻找场景中相关的角色，然后激活调用其领域方法。

设计者的工作就是把这个用例转化为类似交易的算法，如下：

1.源账户开始交易事务   
2.源账户确认余额可用   
3.源账户减少其帐目   
4.源账户请求目标账户增加其帐目  
5.源账户请求目标账户更新其日志 log   
6.源账户结束交易事务   
7.源账户显示给账户拥有人转账成功。  
```
template <class ConcreteAccountType>
class TransferMoneySourceAccount: public MoneySource
{
private:
 ConcreteDerived *const self() {
    return static_cast<ConcreteDerived*>(this);
 }
 void transferTo(Currency amount) {
    // This code is reviewable and
    // meaningfully testable with stubs!
    beginTransaction();
    if (self()->availableBalance() < amount) {
      endTransaction();
      throw InsufficientFunds();
    } else {
      self()->decreaseBalance(amount);
      recipient()->increaseBalance (amount);
      self()->updateLog("Transfer Out", DateTime(),
                amount);
      recipient()->updateLog("Transfer In",
             DateTime(), amount);
    }
    gui->displayScreen(SUCCESS_DEPOSIT_SCREEN);
    endTransaction();
 }
```
