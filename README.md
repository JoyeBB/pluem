
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    <center>
        <h3>吃了吗</h3>
        <textarea id="text" rows="10" cols="50"></textarea>
        <br>
        <button id="button">检测</button>
    </center>
</body>
<script  src="jquery.min.js"></script>
<script>
    var keywords=['是男的','我家','糊摇直下',
                '蒸煮','青组','可吗','抱走',
                '是女的','不做瓜','放过','独美',
                '不做花','霸凌','大虎队','好帅',
                '可不可','正主','创造营','你家'
                ];
    var subwords=['【是男的】','【我家】','【糊摇直下】',
                '【蒸煮】','【青组】','【可吗】','【抱走】',
                '【是女的】','【不做瓜】','【放过】','【独美】',
                '【不做花】','【霸凌】','【大虎队】','【好帅】',
                '【可不可】','【正主】','【创造营】','【你家】'
                ];
    $('#button').click(function () {
        var value = $("#text").val();
	    for(var i=0;i<keywords.length;i++){
		    var reg = new RegExp(keywords[i],"g");
            if(value.indexOf(keywords[i])!=-1){
                var result=value.replace(reg,subwords[i]);
                value=result;
                $("#text").val(result);
            }
	    }
    });
</script>
</html>
