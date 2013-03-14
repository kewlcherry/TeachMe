'use strict';

/* Controllers */


function homeCtrl() {
}
homeCtrl.$inject = [];

function headerCtrl($scope,$http) {
	$scope.notLogin=true;
	nexus.headerScope = $scope;
	
	$scope.logout=function($http){
		this.notLogin=true;
		
	};
}
headerCtrl.$inject = ['$scope','$http'];

function loginCtrl($scope,$http,$location) {
	nexus.loginForm=$scope;
	$scope.login = function (){
		if($scope.username==='' || typeof $scope.username === "undefined"
				|| $scope.password==='' || typeof $scope.password === "undefined"){// have to add json call
			$scope.error='invalid user name/ password';
		}else{
			nexus.headerScope.notLogin = false;
			$scope.dismiss();
				var getType = {};
				if(nexus.loginForm.turl  && getType.toString.call(nexus.loginForm.turl ) === '[object Function]'){
					nexus.loginForm.turl();
				}
				nexus.loginForm.turl=function(){};
		}
	};
}
loginCtrl.$inject = ['$scope','$http','$location'];