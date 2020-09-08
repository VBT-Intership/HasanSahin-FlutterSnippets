# Flutter Snippets - Lazy Class, MVVM Structure, Http View Model

	"Create Lazy Class": {
		"scope": "dart",
		"prefix": "lazyClass",
		"body": [
			"class $1 {",
				"static $1 _instance;",
				"static $1 get instance {",
					"if (_instance == null) _instance = $1._init();",
						"return _instance;",
				"}",
				"$1._init();",
			"}"
		],
		"description": "Lazy Class Pattern"
	},
	"Create Base Model Class": {
		"scope": "dart",
		"prefix": "baseModel",
		"body": [
			"abstract class BaseModel<T> {",
				"Map<String, Object> toJson();",
				"T fromJson(Map<String, Object> json);",
			"}"
		],
		"description": "Base Model Class"
	},
	"MVVM Base Class": {
		"scope": "dart",
		"prefix": "MVVMbase",
		"body": [
			"import 'package:flutter/material.dart';",
			"class $1 extends StatefulWidget {",
				"@override",
				"$1View createState() => new $1View();",
			"}"
		],
		"description": "MVVM Base Class"
	},
	"MVVM View Class": {
		"scope": "dart",
		"prefix": "MVVMview",
		"body": [
			"import 'package:flutter/material.dart';",
			"class $1View extends $1ViewModel {",
				"@override",
				"Widget build(BuildContext context) {",
					"return Text('Just a placeholder');",
				"}",
			"}"
		],
		"description": "MVVM View Class"
	},
	"MVVM View Model Class": {
		"scope": "dart",
		"prefix": "MVVMviewModel",
		"body": [
			"import 'package:flutter/material.dart';",
			"abstract class $1ViewModel extends State<$1> {",
			"",
			"}"
		],
		"description": "MVVM View Model Class"
	},
	"Http Request View Model": {
		"scope": "dart",
		"prefix": "httpViewModel",
		"body": [
			"bool isLoading = false;",
			"Future<void> $1() async {",
				"changeLoading();",
				"try {",
					"$2 = await $3;",
				"} catch (e) {",
					"showErrorDialog(e.toString());",
				"}",
				"changeLoading();",
			"}",
			"void showErrorDialog(String message) {",
				"showDialog(",
					"context: context,",
				"builder: (context) => Dialog(",
					"child: Text(message),",
					"),",
				");",
			"}",
			"void changeLoading() {",
				"setState(() {",
					"isLoading = !isLoading;",
				"});",
			"}",
		],
		"description": "Http Request View Model"
	},
