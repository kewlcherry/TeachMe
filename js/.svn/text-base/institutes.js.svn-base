'use strict';

/* Controllers */


function instituteCtrl($scope,$http) {
	$http.get('institute/all.json').success(function(data) {
    $scope.institutes = data;
  });
}
instituteCtrl.$inject = ['$scope','$http'];//inject required
