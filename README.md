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
