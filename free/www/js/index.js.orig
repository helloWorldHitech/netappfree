var app = {
    initialize: function() {
        this.bindEvents();
    },
    bindEvents: function() {
        document.addEventListener('deviceready', this.onDeviceReady, false);
        document.addEventListener('pause', this.onPause, false);
        document.addEventListener('resume', this.onDeviceReady, false);
        document.addEventListener('online', this.onDeviceReady, false);
        document.addEventListener('offline', this.onPause, false);
        document.addEventListener('backbutton', this.onPause, false);
        document.addEventListener('menubutton', this.onDeviceReady, false);
		
    },
	onPause: function() {
        
    },
    onDeviceReady: function() {
        app.receivedEvent('deviceready');
    },
    receivedEvent: function(id) {
        var parentElement = document.getElementById(id);
        var listeningElement = parentElement.querySelector('.listening');
        var freeElement = parentElement.querySelector('.free');
        var halfElement = parentElement.querySelector('.half');
        var busyElement = parentElement.querySelector('.busy');
        var errorElement = parentElement.querySelector('.error');
		
		var xmlhttp = new XMLHttpRequest();
		var url = "http://dweet.io/get/latest/dweet/for/hackatonFeb2016";
		
		xmlhttp.onreadystatechange = function() {
			if (xmlhttp.readyState == 4) {
                if (xmlhttp.status == 200 || xmlhttp.status == 0) {
				    var response = JSON.parse(xmlhttp.responseText);
					var arr = response.with;
					var answer = arr[0].content.toilet1;
					if(answer == 0){
						listeningElement.setAttribute('style', 'display:none;');
						halfElement.setAttribute('style','display:none;');
						busyElement.setAttribute('style','display:none;');
						errorElement.setAttribute('style','display:none;');
						freeElement.setAttribute('style', 'display:block;');
						
					}else if (answer == 1){
						listeningElement.setAttribute('style', 'display:none;');
						halfElement.setAttribute('style','display:block;');
						busyElement.setAttribute('style','display:none;');
						errorElement.setAttribute('style','display:none;');
						freeElement.setAttribute('style', 'display:none;');
					}else if (answer == 2){
						listeningElement.setAttribute('style', 'display:none;');
						halfElement.setAttribute('style','display:none;');
						busyElement.setAttribute('style','display:block;');
						errorElement.setAttribute('style','display:none;');
						freeElement.setAttribute('style', 'display:none;');
						}else {
						listeningElement.setAttribute('style', 'display:none;');
						halfElement.setAttribute('style','display:none;');
						busyElement.setAttribute('style','display:none;');
						errorElement.setAttribute('style','display:block;');
						freeElement.setAttribute('style', 'display:none;');					}
				}
			}
		}
		xmlhttp.open("GET", url, true);
		xmlhttp.send();
    }
};