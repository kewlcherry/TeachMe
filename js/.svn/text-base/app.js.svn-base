'use strict';


var nexus={};
//angular.module('angularjs-starter', []);

// Declare app level module which depends on filters, and services
var App=angular.module('nexus', ['$strap.directives','nexus.filters', 'nexus.services', 'nexus.directives']).
  config(['$routeProvider', function($routeProvider) {
  //routig config and link to /courses will palce the courses.html in  <div ng-view></div> of index.html
    $routeProvider.when('/course', {templateUrl: 'partials/courses.html', controller: courseCtrl,view:'main'});
    $routeProvider.when('/institute', {templateUrl: 'partials/institutes.html', controller: instituteCtrl,view:'main'});
	$routeProvider.when('/course/:courseId', {templateUrl: 'partials/course-detail.html', controller: courseDetailCtrl,view:'main'});
    $routeProvider.when('/home', {templateUrl: 'partials/home.html', controller: homeCtrl,view:'main'});
	$routeProvider.when('/learnCourse/:courseId', {templateUrl: 'partials/learn-corse.html', controller: learnCourseCtrl,view:'main'});
	$routeProvider.when('/course/section/:sectionId', {templateUrl: 'partials/section.html', controller: sectionCtrl,view:'section'});
	$routeProvider.when('/test/:courseId', {templateUrl: 'partials/plugins/test.html', controller: testPluginCtrl,view:'section'});
	$routeProvider.when('/playcard/:courseId', {templateUrl: 'partials/plugins/playcard.html', controller: playCardPluginCtrl,view:'section'});
	$routeProvider.when('/practice/:courseId', {templateUrl: 'partials/plugins/practice.html', controller: practicePluginCtrl,view:'section'});
	$routeProvider.when('/', {templateUrl: 'partials/home.html', controller: homeCtrl,view:'main'});
    $routeProvider.otherwise({redirectTo: '/home',view:'main'});
	  
  }]);
