#### 注册一个空物品
添加物品变量：
``` java
public static Item item;
```
注册物品，添加到预初始化里：
``` java
item = new item().setUnlocalizedName(String itemIDName);    //添加物品，并设置非本地化名称，一定要全小写
GameRegistry.registerItem(item, item.getUnlocalizedName().substring(5));    //注册物品
```
`item.getUnlocalizedName().substring(5)` 里 `item.getUnlocalizedName()` 的值为 `setUnlocalizedName(String itemIDName)` 里设置的ID名称+前缀“item.”，所以才要用substring来去掉前缀

写完以上代码发现显示报错，那是因为不知道 `item()` 是什么东西，所以添加一个类，类名与 `item()` 中的item一样：
``` java
import net.minecraft.item.Item;

public class item extends Item {
}
```
#### 设置物品名称
在“resources\assets\modid\lang”目录里新建文件“en_US.lang”（美式英文语言文件）、“zh_CN.lang”（简中语言文件），还有其他语言的语言文件，前面文件夹没有的自己建，“modid”填对应的modid。
在对应语言文件里输入：
```
item.itemIDName.name=itemName
```
例：itemIDName为apple，英文文件里itemName为Apple，中文文件里itemName为苹果，这样游戏里物品显示的名称就是“Apple”/“苹果”而不是 `item.apple.name`了

Adding a Texture