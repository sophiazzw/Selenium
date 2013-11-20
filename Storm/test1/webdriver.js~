//var webdriver = require('selenium-webdriver');
//var driver = new webdriver.Builder().withCapabilities(webdriver.Capabilities.chrome()).build();
//driver.get('http://www.google.com');
//driver.findElement(webdriver.By.name('btnG')).click();
//driver.wait(function(){
//	return driver.getTitle().then(function(title){
//	return title === 'webdriver - Google Search';
//	});
//},1000);

//driver.quit();
var assert = require('assert'),
	fs     = require('fs'),
    request   = require('request');
//var webdriver = require('selenium-webdriver');
//var driver = new webdriver.Builder().withCapabilities(webdriver.Capabilities.chrome()).build();
//client = webdriverjs.remote({
//        desiredCapabilities: {
//            browserName: 'chrome',
//            version: '27',
//            platform: 'XP',
//            tags: ['examples'],
//            name: 'This is an example test'
//        },
//        host: 'ondemand.saucelabs.com',
//        port: 80,
//        user: process.env.SAUCE_USERNAME,
//        key: process.env.SAUCE_ACCESS_KEY,
//        logLevel: 'silent'
//    }).init();
var webdriverjs = require('webdriverjs'),
    client = {};
var chai = require('chai');    
var expect = chai.expect;
var options = {
	browserName: 'firefox',
    version: '27',
    platform: 'win7',
    tags: ['JJsHouse','API'],
    name: 'JJsHouse API test',
//	desiredCapabilities:capabilities,
//	host: 'ondemand.saucelabs.com', // Sauce Labs remote host
//	port: 80,
//    build: process.env.TRAVIS_BUILD_NUMBER ? 'build' + process.env.TRAVIS_BUILD_NUMBER : new Date().getTime(),
//    username: process.env.SAUCE_USERNAME,
//    accessKey: process.env.SAUCE_ACCESS_KEY,
//    user: process.env.SAUCE_USERNAME,
//    key: process.env.SAUCE_ACCESS_KEY,
//    'record-video': true,
//    'record-screenshots': true  
};
function allPrpos(obj){
	var props = '';
	for(var p in obj){
		console.log(p);
	}
}
describe('my JJsHouse tests', function(){
    this.timeout(999999);
    before(function(done){
        client = webdriverjs.remote(options);
        client.init();
        client.url('http://www.jjshouse.com/');
        done();
            //allPrpos(client);
    });
    it('execute a javascript',function(done){
    	var Js = 'function getCategoryUrl(){'+
					 'var items = $(\'#nav li\');'+
					 'var urls = [];'+
					 '$.each(items, function(index, val) {'+
						 'var url = $(val).find(\'strong\').text();'+
						 'if(url){'+
							 'urls.push(url);'+
						 '}'+
					 '});'+
					 'return urls;'+
				 '}';
    	client.execute(Js,function(err,res){
    		expect(err).to.be.null;
    		console.log(res);
    	}).call(done);
    });
    after(function(done) {
    	client.end(done);
    });
});
