'use strict';

/* Controllers */


function courseCtrl($scope,$http) {
	$http.get('course/all.json').success(function(data) {
    $scope.courses = data;
  });
}
courseCtrl.$inject = ['$scope','$http'];//inject required



function courseDetailCtrl($scope, $routeParams, $http,$location) {
	$scope.joinCourse=function(){
		  if(nexus.headerScope.notLogin){
			 nexus.loginForm.show();
			//alert($location.path());
			nexus.loginForm.turl=function(){
				$location.path('/learnCourse/'+$scope.course.id);
			};
			return;
		  }
		  
		$location.path('/learnCourse/'+$scope.course.id);
	};
  $http.get('course/' + $routeParams.courseId + '.json').success(function(data) {
    $scope.course = data;
  });
}
courseDetailCtrl.$inject = ['$scope','$routeParams','$http','$location'];//inject required


function learnCourseCtrl($scope, $routeParams, $http,$location) {
    if(nexus.headerScope.notLogin){
	  nexus.loginForm.show();
	  return;
  }
  
  $http.get('course/complete/' + $routeParams.courseId + '.json').success(function(data) {
    $scope.course = data;
	//alert(data);
  });
}
learnCourseCtrl.$inject = ['$scope','$routeParams','$http','$location'];//inject required

function sectionCtrl($scope, $routeParams, $http) {
  $http.get('course/section/' + $routeParams.sectionId + '.json').success(function(data) {
    $scope.section = data;
	$scope.isVideo= $scope.section.resourseType==='video';
	$scope.isImg= $scope.section.resourseType==='imgs';
	$scope.imgUrlIndex=0;
	$scope.imageMaxIndex=$scope.section.resource.length;
	$scope.nextImage=function(){
		$scope.imgUrlIndex++;
		if($scope.imgUrlIndex>$scope.imageMaxIndex)$scope.imgUrlIndex=0;
	};
	
  });
}
sectionCtrl.$inject = ['$scope','$routeParams','$http'];//inject required


function testPluginCtrl($scope, $routeParams, $http) {
  $http.get('course/test/1.json').success(function(data) {
    $scope.questions = data;
  });
}
testPluginCtrl.$inject = ['$scope','$routeParams','$http'];//inject required

function playCardPluginCtrl($scope, $routeParams, $http) {
  $http.get('course/playcard/1.json').success(function(data) {
	//  alert('in play card'+data);
    $scope.playcards = data;
	$scope.cardCnt=$scope.playcards.length;
	$scope.answer='';
	$scope.cardIdx=0;
	$scope.nextRandomCard=function(){
		$scope.answer='';
		$scope.cardIdx = Math.floor( $scope.cardCnt*Math.random() );
	};
	$scope.showAnswer=function(){
		$scope.answer=$scope.playcards[$scope.cardIdx].a;	
	};
	
  });
}
playCardPluginCtrl.$inject = ['$scope','$routeParams','$http'];//inject required


function practicePluginCtrl($scope, $routeParams, $http) {
  $http.get('course/practice/1.json').success(function(data) {
	//  alert('in play card'+data);
    $scope.questions = data;
	$scope.qcount=$scope.questions.length;
	$scope.p=0;
	$scope.noOfHints=$scope.questions[$scope.p].hints.length;
	$scope.answer=$scope.questions[$scope.p].a;
	$scope.question=$scope.questions[$scope.p].q;
	$scope.sHints=[];
	
	$scope.message="";
	
	$scope.nextHint=function(){
		if($scope.noOfHints===$scope.sHints.length){
			alert('You Jaffa answer is solved!!');
			return;
		}
		$scope.sHints.push($scope.questions[$scope.p].hints[$scope.sHints.length]);
	};
	$scope.validate=function(){
		if($scope.answer===$scope.uans){
			$scope.message="Correct";
		}else{
			$scope.message="Wrong";
		}
	};
	
  });
}
practicePluginCtrl.$inject = ['$scope','$routeParams','$http'];//inject required