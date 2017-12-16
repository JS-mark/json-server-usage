### 前后端并行开发的痛点
- 前端需要等待后端开发完接口以后 再根据接口来完成前端的业务逻辑

### 解决方法
- 在本地模拟后端接口用来测试前端效果 这种做法称之为构建前端Mock

### [json-server](https://github.com/typicode/json-server)
- 获取一个模拟的功能齐全的api接口 不需要敲代码 小于30s即可搞定

### json-server使用
- 全局安装json-server命令行工具
	+ `npm install -g json-server`
- 准备一个json文件
	+ 存储数据 
	+ 生成接口
- 启动
	+ `json-server ./db.json`

### 接口说明
- GET 请求数据列表
	+ localhost:3000/users

- GET 请求指定ID的数据
	+ localhost:3000/users/1

- GET 请求指定字段值的数据
	+ localhost:3000/users?name=李四&name=张三

- GET 数据分页
	+ localhost:3000/users?\_page=1&\_limit=2

- GET 数据排序
	+ localhost:3000/users?\_sort=age&\_order=asc
	+ asc 升序 desc 降序

- GET 区间查询
	+ localhost:3000/users?age_gte=30&age_lte=40

- GET 搜索
	+ localhost:3000/users?q=张三

- GET 关联查询
	+ localhost:3000/companies/1/users

- POST 添加数据
	+ localhost:3000/users
	+ Headers:{ Content-Type:'application/json' }
	+ body -> raw
	```javascript
	{
	    "name": "赵六",
	    "age": 50,
	    "companyId": 3
	}
	```

- delete 删除数据
	+ localhost:3000/users/1

- patch 更新数据
	+ localhost:3000/users/3
	+ Headers:{ Content-Type:'application/json' }
	+ body -> raw
	```javascript
	{
	    "age": 100
	}
	```
