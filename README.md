
## 【打卡第1天】Collection-Set接口与泛型
<br>哈希Set与树Set
<br>
<br>1、迭代器：
<br>Iterator： hasNext()、next()关键字
<br>Iterable：增强for循环能力，适用于简单的遍历
<br>for each循环：for(Object o:a){sout···(o);}
<br>
<br>2、泛型：(当做一些集合的统一操作的时候，需要保证集合类型是统一的，此时需要泛型来进行限制)
<br>优点：
<br>(1)数据安全
<br>(2)获取数据时效率比较高
<br>
<br>泛型的高阶应用：
<br>1、泛型类: 在定义类的时候在类名的后面添加<E,K,V,A,B>,起到占位的作用，类中的方法的返回值类型和属性的类型都可以    使用
<br>
<br>2、泛型接口: 在定义接口的时候，在接口的名称后添加<E,K,V,A,B>,
<br>(1)子类在进行实现的时候，可以不填写泛型的类型，此时在创建具体的子类对象的时候才决定使用什么类型
<br>(2)子类在实现泛型接口的时候，只在实现父类的接口的时候指定父类的泛型类型即可，此时，测试方法中的泛型类型必须要    跟子类保持一致
<br>
<br>3、泛型方法
<br>4、泛型的上限(很少用)
<br>5、泛型的下限(很少用)
<br>
<br>
<br>
<br>
## 【打卡第2天】Map接口
<br>哈希Map与树Map
<br>
<br>1、哈希Map：
<br>数据+链表（JDK 1.7）
<br>数组+链表+红黑树（JDK 1.8）
<br>
<br>2、工作中用的比较多：
<br>(1)哈希Map： 不安全 效率高 （<K , V>） 可以为null
<br>(2)Hashtable： 安全 效率低 （<K , V>）不能为null
<br>(3)树Map：红黑树
<br>(4)LinkdeHashMap：链
<br>
<br>3、哈希Map初始值为2的N次幂：
<br>效率：&>取模运算(20/3 商为6 余数为2，结果就是2了)
<br>如：hash & (初始化的容量-1)
<br>
<br>4、扩容：
<br>就是地址号……0 1111与……1 1111 第五位0与1
<br>若为0：原地址下标添加
<br>若为1：原地址下标+16后继续添加
<br>
<br>原地址下标： 1-2-3-4-5
<br>扩容后的地址下标：6-7-8-9-10
<br>注意：根据红黑树添加规则（平衡添加）
<br>
<br>5、执动函数（了解一下）
<br>
<br>★6、看下reeMap<K,V> ( 装JDK1.7后，Ctrl+左键查看里面注释 )
<br>
<br>
<br>
<br>参考下面一部分：
<br>![image](https://github.com/2556009510/Java/blob/master/%E5%9B%BE%E7%89%87/2%E8%BF%AD%E4%BB%A3%E5%99%A8.png)
<br>
<br>
<br>
<br>
## 【打卡第3天】
<br>Collection接口与Coll...s工具类
<br>Arrays工具类
<br>
<br>1、Arrays：工具类
<br>集合→数组
<br>数组→集合
<br>
<br>2、Collection与Coll…s 的区别：
<br>Collection：集合接口
<br>Coll…s：工具类（包内全是静态方法）
<br>
<br>3、集合与数组的比较：
<br>(1)
<br>      基本数据类型  对象   动态改变
<br>数组   √            √      ×           
<br>集合   ×            √      √    
<br>(2)
<br>①数组: 无法知道元素个数，length只能告诉容量 
<br>②集合: 用size()可以知道元素个数
<br>
<br>(3)
<br>集合以类的形式存在，具有封装、继承、多态等一些类的特点
<br>
<br>
<br>
<br>
<br>
## 【打卡第4天】IO流
<br>1、File常用方法：
<br>File f = new File("aaa.txt")
<br>
<br>boolean exists( )·················判断文件或目录是否存在
<br>boolean isFile( ) ·················判断是否是文件
<br>boolean isDirectory( ) ············判断是否是目录
<br>String getPath( )···················相对路径
<br>String getAbsolutePath( )··········绝对路径
<br>String getName( ) ·················文件名称
<br>boolean delete( )·······················删除
<br>long length() ·····················返回文件长度(字节)，如果不存在返回OL
<br>boolean createNewFile( )············空文件不能再创建文件夹
<br>
<br>创建文件
<br>File f = File("aaa.txt");
<br>f.createNewFile();（红灯二）
<br>
<br>判断文件属性
<br>f.canExecute();
<br>f.canRead();
<br>f.canWrite();
<br>
<br>sys...(f.getAbsolutePath)；···········获取文件目录
<br>sys···(f.getParent());················当前路径是否包含该文件
<br>sys···(f.getCanonicalPath())；·········文件绝对路径
<br>sys···(File.Separator);················获取文件的分割线
<br>
<br>String[] aa = f1.list();
<br>for(String str:aa)
<br>{sys···(aa.toSting(1);}·················该目录下所以文件地址
<br>
<br>File[] bb = f2.listFiles();
<br>for(File ff:bb)
<br>{sys···(ff);}···························该目录下所有文件
<br>
<br>File f3 = File.listRoots();
<br>for(int i=0,i<f3.length;i++)
<br>{sys···(f3[i]);}·························电脑所有盘
<br>
<br>File f4 = new File("C:/a");
<br>f3.mkdir();································创建单级目录
<br>
<br>File f5 = new File("C:/a/b/c");
<br>f5.mkdirs();·······························创建多级目录
<br>
<br>
<br>
<br>
## 【打卡第5天】IO流
<br>
<br>flush()·····（当关掉水龙头后，将管道内剩下的水输到容器）
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>![image]()
<br>![image]()
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


