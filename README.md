# SOS
  <body>
  <h6>What is going on?</h6>

<form >
<input type="radio" name="choice" value="Robbed"> Robbed
<input type="radio" name="choice" value="Harrased"> Harrased
<input type="radio" name="choice" value="Kidnapped"> Kidnapped
<input type="radio" name="choice" value="Injured"> Injured
</form>
<button>Submit</button>
  <div class="modal fade" id="StudentModal" tabindex="-1" role="dialog" aria-labelledby="StudentModalLabel" aria-hidden="true" data-backdrop="static">
   <div class="modal-dialog">
      <div class="modal-content">
         <form action="~/GetStudent" class="form-horizontal" role="form" method="post" id="frmStudent">
            <div class="modal-footer">
               <div class="pull-right">
                  <button type="submit" class="btn btn-success"><i class="glyphicon glyphicon-ok"></i> Save</button>
                  <button type="button" class="btn btn-danger" data-dismiss="modal"><i class="glyphicon glyphicon-remove"></i> Close</button>
               </div>
            </div>
         </form>
      </div>
   </div>
  
</body>

               
