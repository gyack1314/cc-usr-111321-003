# 业务资料约定

sites坐标属于单位圆；observed=false时failed必须为null，缺少坐标不表示通过。notch_degrees为缺口方向。parent是不可拆分的数据隔离键，campaign表示投产批次先后。

每行id在该表内唯一，文件顺序不代表业务事件顺序。清单schema=1，各表登记文件名、字节长度、SHA256、行数及完整字段集合，未知版本或内容变化应重新登记。金额及测量数值均为独立资料，不代表任何现实机构的经营数据。

- wafers：id、parent、product、campaign、notch_degrees。
- sites：id、wafer、x、y、observed、failed。
- labels：id、wafer、type。

normal与boundary是相互独立的资料包，不能直接拼接重复id。引用字段按本项目domain.py的REFERENCES登记。读取检查只检查完整性、身份及这些直接引用，不替代领域分析中的可识别性、时点可见性或可行性判断。
