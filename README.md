# Bootstrap-Modal-popup-cookies

<div class="modal fade" id="sitepopup" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered" role="document">
    <div class="modal-content">
      <div class="modal-header">       
       
      </div>
      <div class="modal-body"> 
          <button type="button" class="close closesitepopup" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
        Content..
      </div>
     
    </div>
  </div>
</div>   


<script>
         $(document).ready (function() {
        //console.log(getCookie('newsLetter'));
        if(getCookie('sitepopup')!='1') {
            setInterval(function() {
                if(getCookie('sitepopup')!='1') {
                    //$('#newsletter').modal('show'); 
                    $('#sitepopup').modal({backdrop: 'static', keyboard: false});
                }
            }, 2000); 
        }
        
        $(".closesitepopup").click(function(e) {
            //e.preventDefault();
            setCookie('sitepopup', '1', 1);
            $('#sitepopup').modal('hide');
        });
    });
         function setCookie(name, value, days) {
    var d = new Date;
    d.setTime(d.getTime() + 24 * 60 * 60 * 1000 * days);
    document.cookie = name + "=" + value + ";path=/;expires=" + d.toGMTString();
}
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}
function deleteCookie(name) {
    setCookie(name, '', -1);
}
</script>
