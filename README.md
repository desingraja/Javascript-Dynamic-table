# Javascript-Dynamic-table

var array = [1,2,3,4,5,6,7,8,9,10];

var result = "<table border=1>";
result += "<tr>";
for (var j = 0; j < array.length; j++) {
  result += "<td>" + array[j] + "</td>";
  if ((j + 1) % 5 == 0) {
    result += "</tr><tr>";
  }
}
result += "</tr>";
result += "</table>";

document.body.innerHTML = result;

// My demo checking code using ajax here

var hashurl = "http://localhost:3000/hash";
  $.ajax({
          type: "GET", //or GET
          url: hashurl,
          crossDomain:true,
          cache:false,
          async:false,
          success: function(data){
            console.log(data);
            var datahash = data['hash'];
                        
var result = "<table border=1>";

result += "<tr>";
for (var j = 0; j < data['hash'].length; j++) {
  result += "<td>" + data['hash'][j]['hashes'] + "</td>";
  if ((j + 1) % 1 == 0) {
    result += "</tr><tr>";
  }
}
result += "</tr>";
result += "</table>";

 document.getElementById('table').innerHTML = result;
          }
          })
