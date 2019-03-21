<template>
  <div class="read-more example">
    <div id="xmpl-3">
      <h3>Toggle full story</h3>
      <p><em>Lorem Ipsum</em> is simply <strong>dummy text</strong> of the printing and typesetting industry.
        It has been the industry's standard dummy text ever <strong>since the 1500s</strong>, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
        <em>Lorem Ipsum</em> has survived not only <strong>five centuries</strong>, but also the leap into <strong>electronic typesetting</strong>, remaining essentially unchanged.</p>
      <a class="toggle" href="#"></a>
    </div>
  </div>
</template>

<script>
  import Dotdotdot from "dotdotdot-js/dist/dotdotdot.es6.js";
  export default {
    data() {
      return {}
    },
    mounted() {
      const xmpl = document.querySelector( '#xmpl-3' );
      const dot = new Dotdotdot( xmpl, {
        // Prevents the <a class="toggle" /> from being removed
        keep: '.toggle'
      })

      // Get the dotdotdot API
      const api = dot.API;

      xmpl.addEventListener( 'click', ( evnt ) => {
        if ( evnt.target.closest( '.toggle' ) ) {
          evnt.preventDefault();
          //	When truncated, restore
          if ( xmpl.matches( '.ddd-truncated' ) )
          {
            api.restore();
            xmpl.classList.add( 'full-story' );
          }
          //	Not truncated, truncate
          else
          {
            xmpl.classList.remove( 'full-story' );
            api.truncate();
            api.watch();
          }
        }
      });
    }
  }
</script>

<style scoped>
.read-more {
  width: 200px;
}

.example > .full-story {
  max-height: initial;
}
.example .toggle:before {
  content: 'Show more';
}
.example > .full-story .toggle:before {
  content: 'Show less';
}
</style>
