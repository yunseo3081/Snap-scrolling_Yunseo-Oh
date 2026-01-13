let pages = document.querySelectorAll(".page");
let currentPage = 0;
let canScroll = true;
window.addEventListener("wheel", function (event) {
    if (canScroll === false) {
        return;
    }

    if(event.deltaY>0) {
        currentPage = currentPage+1;
    } else {
        currentPage = currentPage-1;
    }
    if(currentPage<0) {
        currentPage = 0;
    }
    if(currentPage>pages.length-1){
        currentPage = pages.length -1;
    }
    canScroll=false;
    pages[currentPage].scrollIntoView ({
        behavior: "smooth"
    
    });
    setTimeout(function(){
        canScroll = true;
    }, 800);
});
