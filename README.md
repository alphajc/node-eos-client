# node-eos-client
restify客户端，作为Save项目的一部分，向eos-core发送rest请求，并接受返回信息。该客户端将被其他模块调用，如eos-adminui。

# 使用说明
1. 安装eos-client：
      
      npm安装：`npm install eos-client --save`

      yarn安装：`yarn add eos-client`

2. 创建客户端：

    ```js
    /**
     * @params {object} opts
     *  - opts.core_addr {string} core地址
     *  - opts.core_port {number} core端口
     */
    let client = require('eos-client').createClient(opts, 
    /*
     * @params {object} err 错误对象，当有错误时，err不为空，否则为空，需要进行处理
     * @params {object} res 请求正确时，返回的对象
     */
    (err, res) => {});
    ```

3. 获取列表：
    
    ```js
    /*
     * @params {object} opts 筛选条件，此处应包含uploaded_by
     *  - opts.uploaded_by {string} 上传者uuid 
     *  - opts.type {string} 文件类型
     */
    client.getList(opts, (err, res) => {});
    ```

4. 上传
    
    ```js
    client.upload(opts, (err, res) => {});
    ```

5. 下载
    
    ```js
    client.download(opts, (err, res) => {});
    ```

# 许可
MPL v. 2. See [LICENSE](./LICENSE).
