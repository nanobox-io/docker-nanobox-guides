<template lang="pug">
  .doc.page
    leftnav
    .main
      breadcrumbs
      Content
</template>

<style lang="scss" >
  @import './scss/helpers';
  .doc                 {
    h1,h2,h3,h4,h5,h6  {color:$navy; border-bottom:solid 1px #E1E9ED; margin-bottom:0;padding-bottom:0.2em;
      a                {color:inherit; position:relative;
        &:before       {content:"#"; opacity:0; transition: opacity 300ms; position:absolute; left:-0.85em; font-size:24px; font-style:normal; color:#D8DDE0; }
        &:hover:before {opacity:1; }
      }
    }
    h2,h3,h4,h5,h6     {padding:.5em 0;
      & + p            {margin-top:15px;}
    }
    h1, h2             {text-transform:uppercase; letter-spacing:0.05em; line-height:1em;}
    h1                 {font-size:36px; margin-top:20px; padding-bottom:30px;
      a:before         {top:10px;}
    }
    h2                 {letter-spacing:0.03em;margin-top:40px; font-size:24px;}
    // h3                 {font-size:21px;}
    h3,
    h4                 {font-size:18px; font-style:italic;
      a:before         {font-size:20px; left:-0.7em;}
    }
    p,ul,ol            {color:#738792; font-size:17px; font-weight:$medium; line-height: 1.65em; margin:25px 0;
      code             {color:#395465; font-weight:bold; padding:4px 8px 6px; background:$bg; white-space:nowrap;}
      a code           {border-bottom: 1px dotted #26BBFF;}
    }
    img                {display:block; margin:0 auto; max-width:100%;}
    table              {width:100%; margin:10px 0 30px; border-spacing:0; border-collapse:initial; color:#738792; font-size: 17px;
      th               {padding:.65em .75em; background:$navy; color: #fff; border-right: 1px solid #48728c;
        &:last-child   {border: none;}
      }
      tr:nth-child(2n) {background:$bg;}
      td               {padding:.65em .75em; border-bottom:1px solid #d6d6d6; border-right:1px solid #d6d6d6;
        &:first-child  {border-left:1px solid #d6d6d6;}
        code           {font-weight:$semibold; color:$navy;}
      }
    }
    // .frameworks        {display:flex; margin-top:20px;
    //   .hex             {margin-right:35px;width:auto;}
    // }
    .icon-crumbs       {display: flex; position: absolute; right:0; top:-43px;
      .icon            {width:31px; margin-left:7px;}
    }
    @media screen and (max-width:700px)
                     {
      .left          {display:none; }
      .main          {width:100%;
        .breadcrumbs {padding-left:10px; }
        .icon-crumbs {padding-right:10px; }
      }
    }
    @media screen and (max-width:700px)
                     {
      .main{
        h1{font-size:35px;}
        h2{font-size:22px;}
        h3{font-size:16px;}
        h4{font-size:14px;}
      }
    }
  }
</style>

<script lang="coffee">
  import breadcrumbs from './breadcrumbs'
  import leftnav     from './leftnav'
  export default
    name: 'doc'
    components : {breadcrumbs, leftnav}
</script>
