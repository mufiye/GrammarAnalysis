# GrammarAnalysis
编译原理语法分析程序
使用了递归下降的语法分析方法，在语法分析之前进行了词法分析，词法分析可见我的另一个仓库中的代码

语法分析的文法如下(o表示空):
* S -> variable=E;S | o	
* E -> E+T | E-T | T	
* T -> T*F | T/F | F	
* F -> (E) | i	

上述文法消除左递归后：	
* S -> variable=E;S | o	
* E -> TG	
* G -> +TG | -TG | o	
* T -> FH	
* H -> *FH | /FH | o	
* F -> (E) | variable	
