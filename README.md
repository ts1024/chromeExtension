# chromeExtension



Util.createPopup = function (url, obj){
	if (!url) return;
	if (!obj) obj = {};
	var width = obj.width || 600;
	var height = obj.height || 400;
	
	chrome.windows.getCurrent(function (wInfo){
		chrome.windows.create({
			url: url,
			type: "popup",
			width: width,
			height: height,
			// 今のウィンドウの中央に表示
			left: wInfo.left + ((wInfo.width - width) / 2 | 0),
			top: wInfo.top + ((wInfo.height - height) / 2 | 0)
		});
	});
};
