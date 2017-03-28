### Instruction Of webpack-hash-sync

webpack-hash-sync is a plugin of webpack. It solves the problem that when we use the command webpack but the file name of javascript file linked by the html is not changed(We are willing to use hash or chunkhash so the name of the javascript file should be synchronized each time).

#### Download:

```
npm install webpack-hash-sync
```

#### Usage

the usage is easy:

```
plugins: [
        //some other plugins...
        new WebpackHashSync({
	      		html:["index.html"],
	            file:["output.*?js","common.*?js"],
	            path:path.join(__dirname, 'public/'),
	            hash:true,
	            chunkhash:false
        }),
        //some other plugins...
],
```

then each time we use `webpack`, the file name of javascript file linked by the html will be synchronized automatically.

*When we use the webpack hot loading，it is also OK. Remember: sometimes we may reload the webpage otherwise we may get 404*

Finally it uses utf-8.

and there is the explaintion of the parameters :

| parameter | Optional | Default | description |
| ------| ------ | ------ | ------ |
| html | Necessary | [] | need to be an array, each is the name of the html file that is needed to be synchronized
| file | Necessary | [] | need to be an array, each is a regular expression of the name of js file |
| path | recommended | "" | the file path of the html file |
| hash | Optional | true | When we use hash, it should be true| 
| chunkhash | Optional | false | When we use chunkhash, it should be true| 


#### Problems

If you have problems, please visit [here](https://github.com/aircloud/webpack-hash-sync/issues) and I will handle the problem in at most 24 hours.

#### Github

https://github.com/aircloud/webpack-hash-sync

#### license

MIT