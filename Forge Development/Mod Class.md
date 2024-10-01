### 主类里
``` java
public class Mod {

}
```

#### @Mod
声明Mod主类
```
@Mod(modid="",name="",version="",...)
```

#### 预初始化
- 初始化并注册物品、方块等
- 配置处理
``` java
@EventHandler
public void preInit(FMLPreInitializationEvent event) {
}
```
#### 初始化
- 注册代理、实体、GUI、数据包等
``` java
@EventHandler
public void init(FMLInitializationEvent event) {
}
```
#### 初始化后
``` java
@EventHandler
public void postInit(FMLPostInitializationEvent event) {
}
```

