# python-
平时做课题时遇到的问题及解决办法
2019.7.17 Datarame中根据数据特征选取数据：
#选取案件类型为1 即火灾类数据
1.读取数据 
filepath = 'C://Users//zhangsheng//Desktop//DSjjcl//version2/new_all_df2.csv'
all_df=pd.read_csv(filepath,encoding='gb18030')
all_df.head()


2. 按需求选取数据
# 火灾
fire_df=all_df[all_df['案件类型']==1]

#拓展
3.对时间类型数据的处理
fire_df['立案时间']=pd.to_datetime(fire_df['立案时间'])  #将时间数据类型转换为to_datetime类型
# 依次读取出to_datetime类型中的 year,month,day,hour,并新增到dataframe列
fire_df['year']=fire_df['立案时间'].dt.year
fire_df['month']=fire_df['立案时间'].dt.month
fire_df['day']=fire_df['立案时间'].dt.day
fire_df['hour']=fire_df['立案时间'].dt.hour
