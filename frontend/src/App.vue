<template>
  <router-view/>
</template>
<style>
.lightgraycolor{
    background: #F5F5F5;
}
.graycolor{
    --tw-text-opacity: 1;
    color: #5A5A5A;
}
.lightgreen{
  background-color: #40d494;
}
.hover\:bg-lightgreen:hover {
    --tw-bg-opacity: 1;
    background-color: #35c184;
}
.bgorange{
    --tw-bg-opacity: 1;
    background-color: #f7b34c;
}

.bgdarkorange{
    --tw-bg-opacity: 1;
    background-color: #d19132;
}

.hover\:bg-bgdarkorange:hover {
    --tw-bg-opacity: 1;
    background-color: #d19132;
}
.bgteal{
    --tw-bg-opacity: 1;
  background-color: #5AC3C3;
}

.hover\:bg-bgteal:hover {
    --tw-bg-opacity: 1;
    background-color: #43abab;
}

/* screen responsiveness if... */
@media (max-width: 1491px) {
    #profile-columns{
        grid-template-columns: repeat(3, minmax(0, 1fr));
    }
}

@media (max-width: 1436px) {
    #if{
        display: flex;
        flex-direction: column;
    }
    #history{
        width: 100%
    }
    #profile-columns{
        grid-template-columns: repeat(3, minmax(0, 1fr));
    }
    #margin{
        margin: 2rem;
    }
    #marginright{
        margin: 1rem;
    }
    #pxlg{
        padding-left: 2rem;
        padding-right: 2rem;
    }
    #px{
        font-size: 11px;
        size: 4;
    }
}

@media (max-width: 1168px) {
    #profile-columns{
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }
    #pxlg{
        padding-left: 1rem;
        padding-right: 1rem;
    }
    #px{
        font-size: 11px;
        size: 4;
    }
    #wide{
        width: 100%;
    }
    #card{
        max-width: 100%;
    }
    #minscreen{
        flex-direction: column;
    }
}

@media (max-width: 1020px) {
    #profile-columns{
        grid-template-columns: repeat(3, minmax(0, 1fr));
    }
    #px{
        padding-left: 2px;
        padding-right: 2px;
    }
    #px{
        font-size: 11px;
        size: 4;
    }
    #feed{
        font-size: 13px;
    }
    #minscreen{
        flex-direction: row;
    }
}

@media (max-width: 875px) {
    #minscreen{
        flex-direction: column;
    }
}
@media (max-width: 770px) {
    #profile-columns{
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }
    #pxlg{
        padding-left: 2rem;
        padding-right: 2rem;
    }
    #minscreen{
        flex-direction: column;
    }
    #wide{
        padding-right: 2.5rem;
        padding-left: 2.5rem;
    }
}

@media (max-width: 550px) {
    #profile-columns{
        grid-template-columns: repeat(1, minmax(0, 1fr));
    }
    #sbuttons{
        gap: 5px;
    }
    #pxlg{
        padding-left: 2rem;
        padding-right: 2rem;
    }
}
/* input[type="date"]::-webkit-input-value {
  visibility: hidden;
} */
</style>