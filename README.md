# devide1
1,
simple 舒服合理结构

2,
simple基础上如何改变先决条件，程序启动后，get，/users/n（数字）

3,
编写koa中间件，get，/users/n（数字）
如何实现
{
    "message": "先决条件失败：id大于数组长度了"
}


4,
npm i koa-json -error --save
koa-json-error
http://localhost:3000/users1111
{
    "message": "Not Found",
    "name": "NotFoundError",
    "stack": "NotFoundError: Not Found\n    at Object.throw (D:\\koa知乎\\舒服的合理结构\\node_modules\\koa\\lib\\context.js:97:11)\n    at next.then (D:\\koa知乎\\舒服的合理结构\\node_modules\\koa-json-error\\lib\\middleware.js:52:58)\n    at process._tickCallback (internal/process/next_tick.js:68:7)",
    "status": 404
}

npm i cross-env --save-dev

package.json:中修改
"scripts": {
    "start": "cross-env NODE_ENV=production node app",
    "dev": "nodemon app"
  },
  
  5,
  npm i koa-parameter --save
  npm run dev
  http://localhost:3000/users(post)
  {
	"name":"天线小宝",
	"age":"0"
}


6,mongoose连接mongodb

7，设计用户模块的schema

8，mongodb增删改查
http://localhost:3000/users（post)
{
	"name":"天线小宝2",
	"age":0
}
得到
{
    "_id": "5e66ea1d89ab4d2088c04536",
    "name": "天线小宝2",
    "__v": 0
}
（get)
http://localhost:3000/users/5e66ea1d89ab4d2088c04536
得到{
    "_id": "5e66ea1d89ab4d2088c04536",
    "name": "天线小宝2",
    "__v": 0
}

添加用户
http://localhost:3000/users/（post)
{
	"name":"天线小宝3",
	"age":0
}
得到
{
    "_id": "5e66ec233393fe307854c81e",
    "name": "天线小宝3",
    "__v": 0
}

获取用户列表
http://localhost:3000/users/

http://localhost:3000/users/（post)
{
	"name":"天线小宝4",
	"age":0
}
得{
    "_id": "5e66ef133393fe307854c820",
    "name": "天线小宝4",
    "__v": 0
}

http://localhost:3000/users/5e66eeff3393fe307854c81f（put)
{
	"name":"天线小宝5",
	"age":0
}
得到
{
    "_id": "5e66eeff3393fe307854c81f",
    "name": "天线小宝5",
    "__v": 0
}

http://localhost:3000/users/5e66eeff3393fe307854c81f（del)
成功！

npm i jsonwebtoken

实现用户注册，看文件1，密码暴露
http://localhost:3000/users/（get）

完善了！！！密码隐藏，put用patch代替，实现单个修改
http://localhost:3000/users/（post)
新建
{
	"name":"天线小宝2",
	"password":"123456"
}
得到
{
    "_id": "5e66fd22c039d93340c0e410",
    "name": "天线小宝2",
    "password": "123456",
    "__v": 0
}
http://localhost:3000/users/5e66fd22c039d93340c0e410（patch)
{
	"name":"2天线小宝",
	"password":"123456"
}
得
{
    "_id": "5e66fd22c039d93340c0e410",
    "name": "2天线小宝",
    "__v": 0
}

http://localhost:3000/users/5e66fd22c039d93340c0e410（patch)
{
	
	"password":"1"
}
得
{
    "_id": "5e66fd22c039d93340c0e410",
    "name": "2天线小宝",
    "__v": 0
}

http://localhost:3000/users/（post)
{
	 "name": "2天线小宝",
	"password":"1"
}
得到
{
    "stack": "ConflictError: 用户已经占用\n    at Object.throw (D:\\koa知乎\\舒服的合理结构\\node_modules\\koa\\lib\\context.js:97:11)\n    at create (D:\\koa知乎\\舒服的合理结构\\app\\controllers\\users.js:24:22)\n    at process._tickCallback (internal/process/next_tick.js:68:7)",
    "message": "用户已经占用",
    "name": "ConflictError",
    "status": 409
}
