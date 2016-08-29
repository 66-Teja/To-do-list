(function() {
  var data = [];
  
  var Utils = {
    uuid: function() {
      function _s4() {
        return Math.floor((1+Math.random())*0x100000).toString(16).substr(1);
      }
      
      return _s4()+_s4()+'-'+_s4()+'-'+_s4()+'-'+_s4()+_s4()+_s4();
    }
  };
  
  var App = {
    start: function() {
      this.$list = $('#todo-list');
      this.$template = Handlebars.compile($('#todo-item').html());
      
      this.events();
      this.render();
    },
    
    events: function() {
      $('#newtodo').on('keyup', this.create.bind(this));
      $('#todo-list').on('click', '.delete', this.removeItem.bind(this));
    },
    
    create: function(event) {
      var $input = $(event.target);
      if(event.keyCode === 13) {
        var newitem = {
          id: Utils.uuid(),
          text: $input.val(),
          completed: false
        };

        data.push(newitem);
        $input.val('');
        this.render();
      }
    },
    
    removeItem: function(event) {
      event.preventDefault();
      var $btn = $(event.target);
      console.log();
    },
    
    render: function() {
      var todoItems = this.$template(data);
      this.$list.html(todoItems);
    }
  };
  
  App.start();
})();
