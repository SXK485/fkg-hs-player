## 关于更新data.json的一些说明
游戏的一些数据会存储在本地的IndexedDB数据库中，IndexedDB数据库在index.js中创建，然后通过请求远程资源进行组装。官方对特殊资源的资源响应进行了加密处理，还要分析加密算法的话不现实，
相比之下想办法获取IndexedDB的明文数据要相对简单得多，而本项目需要的角色基础数据就在IndexedDB数据库里。
原作者在"operation.txt"对如果提取角色数据进行了说明，但实际操作会踩一些坑，详细请查看"提取charaData说明事项.txt"。


## 关于游戏如何获取动态角色列表
尽管官方已经公告暂停发布动态角色了，但还是想说明一下。
同样在IndexedDB数据库，有一个键名"masterCharacterBook"，对应的键值就有角色的名册数据，根据"官方获取动态角色列表的方式.txt"里的操作，可以获取到角色的名册信息，通过heartFlag标志符
可以判断哪一个角色是否拥有动态场景，可以参考我提取出来的"masterCharacterBookList.json"。
