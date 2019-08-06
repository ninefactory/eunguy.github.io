---
title: "apidoc 사용하기"
date: 2019-08-06 10:26:28 -0400
categories: apidoc api
---
apidoc 을 사용해 보자
=====================================

왜?
-------------------------------------
api를 요청 하거나 직접 만들 경우 미래의 나 혹은 같이 작업하는 분께 알려줘야 한다.

기본 개념
-------------------------------------


방법
-------------------------------------
nodeJS 설치 후 

```
npm init
npm install express
npm install apidoc
mkdir myproject
cd myproject
mkdir myapp mytemplate
```
myapp 폴더에 프로젝트 파일 생성
```
apidoc.json

{
  "name": "example",
  "version": "0.1.0",
  "description": "apiDoc basic example",
  "title": "Custom apiDoc browser title",
  "url" : "https://api.github.com/v1"
}
```
myapp 폴더에 api 내용 생성
```
example.js

/**
 * @api {get} /user/:id Request User information
 * @apiName GetUser
 * @apiGroup User
 *
 * @apiParam {Number} id Users unique ID.
 *
 * @apiSuccess {String} firstname Firstname of the User.
 * @apiSuccess {String} lastname  Lastname of the User.
 *
 * @apiSuccessExample Success-Response:
 *     HTTP/1.1 200 OK
 *     {
 *       "firstname": "John",
 *       "lastname": "Doe"
 *     }
 *
 * @apiError UserNotFound The id of the User was not found.
 *
 * @apiErrorExample Error-Response:
 *     HTTP/1.1 404 Not Found
 *     {
 *       "error": "UserNotFound"
 *     }
 */
```
myapp에 작성된 파일들을 이용해 mytemplate에 서비스 파일들을 생성한다. 
당연히,, myproject 폴더에서 실행
```
apidoc -i myapp/ -o apidoc/ 
```






