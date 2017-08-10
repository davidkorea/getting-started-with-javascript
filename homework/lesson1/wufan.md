# 类比代码执行流程

## 1开户的流程

个人到大厅填写申请，递交给窗口工作人员，然后，由工作人员校验/审核资质（这个过程包括1检查信息格式2检查信息准确性；核对1征信2资格），最后要么通过发证，要么驳回重新填写。

优点是结构很简单，缺点是操作效率低下，一次过关率低。

银行开户流程是为了完成一项任务--开户。

#### 四次优化的开户流程

改进后第一版递交给窗口工作人员之间介入了大厅工作人员预处理，类似于氨压缩机预先冷气，然后再膨胀机再制冷，若不这么做，膨胀机入口温度高会导致膨胀机受损。同样预处理后就会方便下一步运行。预处理后，开户申请正确进入窗口环节，错误则驳回重新填写申请。正确申请后，再核对征信和资格，正确则发证，错误则驳回。

改进第二版，省去了递交回个人的步骤，直接由大厅工作人员确认好申请单交给窗口人员。在大厅工作人员环节保证信息正确包括格式和准确性。这就防止了用户的过多负担和反复修改的可能。

改进版三，减少了大厅工作的内容，直接在窗口内的环境完成，窗口内由审查申请和执行申请，组成预处理和执行部分。预处理完交给执行确认好的申请。然后返回到窗口传递到用户那里。

改进版四，窗口内的环境增设了很多内置服务，方便快捷更有针对性服务，因为有了各种模板所以非常快捷便于用户操作。

定义开户流程，用户，银行/开户环境/内置服务、预处理、执行、窗口。

## 2运行环境

运行环境（浏览器、node）就是你要实现你需求必须去什么样的地方，这个地方能够满足你的需求，这就叫运行环境，比如你要洗澡要么去澡堂，要么去自己家里，要么去有干净水源的地方，这个地方就是你实现洗澡目的的环境。

为了实现你的一个业务或者需求，必须从某些内置服务或者第三方库的环境中调用相应的数据，这个环境就是运行环境。

开户环境就是一个办业务的环境，它能提供内置服务，预处理和执行业务的一些列流程。

开户环境：为了完成所需的银行服务必须去银行相关的地方来办理，这个银行就是开户环境。


多样化的业务环境包括普通用户或者VIP，类似于此，js的代码分浏览器业务和nodejs业务环境，代码在不同环境中的语法也是不一样的，编写的方法也不一样。

浏览器中的内置库，就是可以供代码调用的一切函数和第三方库如图所示
node的运行内置库与js只有js内置对象一样，其他的包括第三方库都不一样，所以这两者不能完全兼容，能在js环境跑的，不一定能在node上跑，这也是为什么js可以作为开发前端和后端的工具。
类似于不同的生活环境，js和node的不同环境属性，决定了了他们不能完全兼容，有一部分是可以跑的

业务架构，银行，用户，第三方服务。第三方服务类似于去公安局啊，单位开一些证明材料。
类似于业务架构，JS运行环境框架中，包含了浏览器运行环境，Nodejs运行环境对应的是普通用户的开户环境和VIP用户的开户环境。

输入代码是为了获得想要的结果，这个结果需要一个环境，就好开户只能去银行这个环境一样。如同递交申请和预处理执行审核一样，代码输入也希望能有想要的输出结果。

详细的环境是如何工作的，有代码调用各种库的函数等，再输入用V8引擎去执行。

## 3v8引擎

v8引擎：在编译型或者解释型的过程中，加速执行效率的那么一个内置服务，在黑盒子里。



## 4编译型和解释器

编译型先编译好完整的代码，然后执行。特点是，开发写代码效率低，执行运行快。
解释性是边解释边执行，运行效率低下，但是开发效率高。

编译型就是编译完再一块执行，如果有错误就要逐步检查，开发效率低，但是运行效率高。解释型边解释，边执行，开发效率高，运行相对来说低。
编译的进化之路，由开始的机器语言，到低级指令语言，到后来的间接调用低级语言的高级语言文件，一步步使得编程语言符合我们的自然语言逻辑。

通过阅读优秀代码库，来优化你的程序，更加高效的实现你的目的。

通过研究内置库和第三方库比如freecodecamp等github上排名靠前的js开发库来学习服务与技术之间的差异性，写出合适环境下的代码用于调用出最利于实现你业务的一些库
编程语言学的就是写出优雅的代码调用那些内置库，第三方库。

需要边编译，边执行的机器。

## 5内置库

内置服务：开户时银行内部提供的一组服务。开发环境中固有的一系列服务，比如澡堂有卖拖鞋毛巾等，提供橱柜保管财物的服务。

## 6第三方库



还是澡堂，它没有吃饭的服务，你需要去饭店吃饭，这个饭店就是第三方库，它可能就在澡堂附近。因为众多，所以称库。

第三方服务：银行不具备出具提供的证明等服务，需要由个人实现准备后，才能完成银行内部业务的服务。
核心业务：银行会有哪些直接提供的服务，供你能选择的业务，这些服务和业务就是核心业务。
预处理：在提供服务的时候，为了提高效率减少出错率，采取的有效措施。
执行：就是通过或者驳回客户的各种服务的申请。

第三方库一般都是指同种语言开发的拓展功能，以满足多样化的需求。不排除会用其他语言开发第三方库供JS语言编写的代码来使用。比如：用C语言写一个搞计算法（因为c语言运行效率更高），然后开发接口给js用。那么这个接口比如满足js语言对c语言调用规范。即：两种不同语言之间的调用，比如满足一定的规范，这种规范一般情况只能是这两种语言相互认可。python和c之间的调用会有他们之间的规范。在绝大多数情况下，js不太会用到其他语言的开发库。在学习过程中只聚焦在js的第三方库即可。

## 学习js的方向

分为浏览器的前端开发，和nodejs或者node，后端开发。方向不一样环境也不一样。