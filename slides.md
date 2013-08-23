<h1 class="base0B">Widget-ize All The Things</h1>


<h2 class="base0D">Tyler Benziger</h2>

github.com/tybenz&nbsp;&nbsp;&nbsp;//&nbsp;&nbsp;&nbsp;@tybenz&nbsp;&nbsp;&nbsp;//&nbsp;&nbsp;&nbsp;tybenz.com


### Reduce &#9755; reuse &#9755; refactor


### Reduce ~~&#9755; reuse &#9755; refactor~~


### Reduce ~~&#9755; reuse &#9755;~~ refactor


### ~~Reduce~~ &#9755; reuse &#9754; ~~refactor~~


## Background


# ![](http://awes0.me/adobe2.png) Adobe


![](http://awes0.me/screen_2013-07-11-08-09-21.png)


![](http://awes0.me/screen_2013-07-11-08-07-35.png)


# Here We Go


## The Options

~~Blackbox~~

~~Framework-based~~

~~The Sweet Spot~~


## The Options

Blackbox

~~Framework-based~~

~~The Sweet Spot~~


```javascript
$.fn.secret = function() {

    return this.each(function() {
        var $this = $( this );
        $this.on( 'mousedown', function() { $this.addClass( 'show' ); } );
        $this.on( 'mouseup', function() { $this.removeClass( 'show' ); } );
    });

};

$( '#secret' ).secret();
```


```javascript
{~$.fn.secret = function() {

    return this.each(function() {
        var $this = $( this );
        $this.on( 'mousedown', function() { $this.addClass( 'show' ); } );
        $this.on( 'mouseup', function() { $this.removeClass( 'show' ); } );
    });

};~}

$( '#secret' ).secret();
```


```javascript
$.fn.secret = function() {

    {~return this.each(function() {
        var $this = $( this );
        $this.on( 'mousedown', function() { $this.addClass( 'show' ); } );
        $this.on( 'mouseup', function() { $this.removeClass( 'show' ); } );
    });

};

$( '#secret' ).secret();~}
```


```javascript
{~$.fn.secret = function() {

    ~}return this.each(function() {{~
        {~var $this = $( this );
        $this.on( 'mousedown', function() { $this.addClass( 'show' ); } );
        $this.on( 'mouseup', function() { $this.removeClass( 'show' ); } );
    });

};

$( '#secret' ).secret();~}
```


```javascript
{~$.fn.secret = function() {

    return this.each(function() {
        var $this = $( this );
        ~}$this.on( 'mousedown', function() { $this.addClass( 'show' ); } );{~
        $this.on( 'mouseup', function() { $this.removeClass( 'show' ); } );
    });

};

$( '#secret' ).secret();~}
```


```javascript
{~$.fn.secret = function() {

    return this.each(function() {
        var $this = $( this );
        $this.on( 'mousedown', function() { $this.addClass( 'show' ); } );~}
        $this.on( 'mouseup', function() { $this.removeClass( 'show' ); } );
    {~});

};

$( '#secret' ).secret();~}
```


## The Options

Blackbox

~~Framework-based~~

~~The Sweet Spot~~


## The Options

~~Blackbox~~

Framework-based

~~The Sweet Spot~~


```javascript
var Secret = Backbone.View.extend({
    events: {
        'mousedown': 'apply',
        'mouseup': 'remove'
    },

    apply: function() { this.$el.addClass( 'show' ) },

    remove: function() { this.$el.removeClass( 'show' ) },
});
```


```javascript
{~var Secret = Backbone.View.extend({
    ~}events: {
        'mousedown': 'apply',
        'mouseup': 'remove'
    }{~,

    apply: function() { this.$el.addClass( 'show' ) },

    remove: function() { this.$el.removeClass( 'show' ) },
});~}
```


```javascript
{~var Secret = Backbone.View.extend({
    events: {
        'mousedown': 'apply',
        'mouseup': 'remove'
    },~}

    apply: function() { this.$el.addClass( 'show' ) },

    remove: function() { this.$el.removeClass( 'show' ) },{~
});~}
```


## The Options

~~Blackbox~~

Framework-based

~~The Sweet Spot~~


## The Options

~~Blackbox~~

~~Framework-based~~

The Sweet Spot


### Component Checklist

&#9744; Options

~~&#9744; Browser/User Events~~

~~&#9744; Widget logic~~

~~&#9744; External events~~


### Component Checklist

~~&#9744; Options~~

&#9744; Browser/User Events

~~&#9744; Widget logic~~

~~&#9744; External events~~


### Component Checklist

~~&#9744; Options~~

~~&#9744; Browser/User Events~~

&#9744; Widget logic

~~&#9744; External events~~


### Component Checklist

~~&#9744; Options~~

~~&#9744; Browser/User Events~~

~~&#9744; Widget logic~~

&#9744; External events


```javascript
$.extend( Secret.prototype, widgetMethods, {
    defaultOptions: {
        applyClass: 'show',
        applyEvent: 'mousedown',
        removeEvent: 'mouseup'
    },

    apply: function() { this.$el.addClass( this.options.applyClass ); },

    remove: function() { this.$el.removeClass( this.options.applyClass ); }
});
```


```javascript
{~$.extend( Secret.prototype, widgetMethods, {
    ~}defaultOptions: {
        applyClass: 'show',
        applyEvent: 'mousedown',
        removeEvent: 'mouseup'
    },{~

    apply: function() { this.$el.addClass( this.options.applyClass ); },

    remove: function() { this.$el.removeClass( this.options.applyClass ); }
});~}
```


```javascript
{~$.extend( Secret.prototype, widgetMethods, {
    defaultOptions: {
        applyClass: 'show',
        applyEvent: 'mousedown',
        removeEvent: 'mouseup'
    },~}

    apply: function() { this.$el.addClass( this.options.applyClass ); },

    remove: function() { this.$el.removeClass( this.options.applyClass ); }
{~});~}
```


```javascript
var Secret = function( el, options ) {
    var widget = this;

    this.$el = $( el );

    this.options = $.extend( {}, this.defaultOptions, options );

    this.$el.on( this.options.applyEvent, function() {
        widget.apply();
        widget.trigger( 'secret-apply' );
    });

    this.$el.on( this.options.removeEvent, function() {
        widget.remove();
        widget.trigger( 'secret-remove' );
    });
};
```


```javascript
{~var Secret = function( el, options ) {
    var widget = this;

    this.$el = $( el );~}

    this.options = $.extend( {}, this.defaultOptions, options );

    {~this.$el.on( this.options.applyEvent, function() {
        widget.apply();
        widget.trigger( 'secret-apply' );
    });

    this.$el.on( this.options.removeEvent, function() {
        widget.remove();
        widget.trigger( 'secret-remove' );
    });
};~}
```


```javascript
{~var Secret = function( el, options ) {
    var widget = this;

    this.$el = $( el );

    this.options = $.extend( {}, this.defaultOptions, options );

    this.$el.on(~} this.options.applyEvent{~, function() {
        widget.apply();
        widget.trigger( 'secret-apply' );
    });

    this.$el.on( this.options.removeEvent, function() {
        widget.remove();
        widget.trigger( 'secret-remove' );
    });
};~}
```


```javascript
{~var Secret = function( el, options ) {
    var widget = this;

    this.$el = $( el );

    this.options = $.extend( {}, this.defaultOptions, options );

    this.$el.on( this.options.applyEvent, function() {
        ~}widget.apply();{~
        widget.trigger( 'secret-apply' );
    });

    this.$el.on( this.options.removeEvent, function() {
        widget.remove();
        widget.trigger( 'secret-remove' );
    });
};~}
```


```javascript
{~var Secret = function( el, options ) {
    var widget = this;

    this.$el = $( el );

    this.options = $.extend( {}, this.defaultOptions, options );

    this.$el.on( this.options.applyEvent, function() {
        widget.apply();
        ~}widget.trigger( 'secret-apply' );{~
    });

    this.$el.on( this.options.removeEvent, function() {
        widget.remove();
        widget.trigger( 'secret-remove' );
    });
};~}
```


### Component Checklist

&#9744; Options

&#9744; Browser/User Events

&#9744; Widget logic

&#9744; External events


### Component Checklist

&#9746; Options

&#9744; Browser/User Events

&#9744; Widget logic

&#9744; External events


### Component Checklist

&#9746; Options

&#9746; Browser/User Events

&#9744; Widget logic

&#9744; External events


### Component Checklist

&#9746; Options

&#9746; Browser/User Events

&#9746; Widget logic

&#9744; External events


### Component Checklist

&#9746; Options

&#9746; Browser/User Events

&#9746; Widget logic

&#9746; External events


# Time to extend


```javascript
var secret1 = new Secret( $( '#window1' ) ),
    secret2 = new Secret( $( '#window2' ) );{~

secret1.on( 'secret-apply', function() {
    secret2.apply();
});

secret1.on( 'secret-remove', function() {
    secret2.remove();
});~}
```


```javascript
{~var secret1 = new Secret( $( '#window1' ) ),
    secret2 = new Secret( $( '#window2' ) );~}

secret1.on( 'secret-apply', function() {
    secret2.apply();
});

{~secret1.on( 'secret-remove', function() {
    secret2.remove();
});~}
```


```javascript
{~var secret1 = new Secret( $( '#window1' ) ),
    secret2 = new Secret( $( '#window2' ) );

secret1.on( 'secret-apply', function() {
    secret2.apply();
});~}

secret1.on( 'secret-remove', function() {
    secret2.remove();
});
```


# Scrubber


```javascript
$( '.window' ).each( function() {
    var secret = new Secret( this, {
        applyEvent: 'mouseover',
        removeEvent: 'mouseout'
    });
});
```


```javascript
{~$( '.window' ).~}each{~( function() {
    var secret = new Secret( this, {
        applyEvent: 'mouseover',
        removeEvent: 'mouseout'
    });
});~}
```


```javascript
{~$( '.window' ).each( function() {
    var secret = ~}new Secret{~( this, {
        applyEvent: 'mouseover',
        removeEvent: 'mouseout'
    });
});~}
```


```javascript
{~$( '.window' ).each( function() {
    var secret = new Secret( this, {
        ~}applyEvent: 'mouseover'{~,
        removeEvent: 'mouseout'
    });
});~}
```


```javascript
{~$( '.window' ).each( function() {
    var secret = new Secret( this, {
        applyEvent: 'mouseover',
        ~}removeEvent: 'mouseout'{~
    });
});~}
```


# Recap


# ![](http://awes0.me/copy-paste-ftw.png)


# ![](http://awes0.me/integrate.png)


# ![](http://awes0.me/ignore.jpg)


<h2 class="base0C">A&#9837;$+r@&#9770;&#10015;|&theta;N</h2>


# ![](http://awes0.me/slider.gif)


# ![](http://awes0.me/colorpicker.gif)


# ![](http://awes0.me/kahn-menu.gif)


# ![](http://awes0.me/radial-menu.gif)


# Go <span class="base0B">Forth</span>!


<h2 class="base0D">Tyler Benziger</h2>

github.com/tybenz&nbsp;&nbsp;&nbsp;//&nbsp;&nbsp;&nbsp;@tybenz&nbsp;&nbsp;&nbsp;//&nbsp;&nbsp;&nbsp;tybenz.com


# Questions?
