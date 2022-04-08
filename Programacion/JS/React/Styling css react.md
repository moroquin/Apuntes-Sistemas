In this post we are going to style with css our react app. 



"css-loader": "^6.7.1",

"html-webpack-plugin": "^5.5.0",

"standard": "^16.0.4",

"style-loader": "^3.3.1",







{

test: /\.css$/i,

use: ["style-loader", "css-loader"],

}