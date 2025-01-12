cafe24 쇼핑몰 솔루션
=

## 가입
1. 개인으로 가입
    - 사업자로 가입해도 사업자로 인증되는 것은 아님

## 기본세팅
1. 이용약관, 개인정보처리방침 업데이트
2. 쇼핑몰 정보 (PG 관련 고지정보)
    - 상호, 대표자, 주소, 전화, 사업자번호, 통판, 개인정보보호책임자
3. 결제(PG) 신청, 심사
    - 쇼핑몰 고지정보(+통판), 샘플상품 2개 이상
    - 상품 세팅 (썸네일, 상품명, 가격)
4. 검색엔진최적화(SEO)
    - 쇼핑몰 설정 - 기본 설정 - 내 쇼핑몰 설정
    - 쇼핑몰 이름(title), 쇼핑몰 안내(description)
5. 검색엔진최적화 (SEO)
    - 네이버 서치 어드바이저
        - https://searchadvisor.naver.com/
    - 구글 서치 콘솔
        - https://search.google.com/search-console
6. 도메인 연결, 대표 도메인 설정
    - 카페24 쇼핑몰 네임서버
    ```
    1차 dns1.cafe24.com / IP (175.125.93.130)
    2차 dns1.cafe24.co.kr / IP (112.175.246.229)
    3차 dns2.cafe24.com / IP (175.125.93.140)
    4차 dns2.cafe24.co.kr / IP (112.175.247.229)
    ```

## PG 심사 이후
1. 네이버 쇼핑(가격비교) 입점 신청
    - https://join.shopping.naver.com
2. 네이버 검색광고 가입
    - https://searchad.naver.com
3. 상품 상세페이지 업데이트/업그레이드
4. 상품 등록(수정) 화면에서 `이미지 사이즈 변경`
    - 상세, 목록, 작은목록, 축소, 확대 모두 `1,000px`

## 카페24PRO

## 스마트디자인 Easy 수정
1. 상단 메뉴
    1. 메뉴 - 카테고리(분류) 설정 후 '상품 분류 동기화' 하고 나서
    2. '상위 메뉴 추가'로 게시판, 페이지 등 추가
2. 무통장 계좌
    1. 대표 번호/이메일 인증 후
    2. 결제 설정 - 무통장입금 계좌 설정
    3. 디자인 - 푸터 - 결제 정보 - 계좌 정보 동기화
3. 섹션 추가는 - 커스텀 HTML로 할 것

## 스마트디자인 모듈
https://sdsupport.cafe24.com
- 모듈리스트
    - https://sdsupport.cafe24.com/product/list.html?cate_no=61
- 모디파이어
    - https://sdsupport.cafe24.com/board/tip/read.html?no=92&board_no=6
    - https://sdsupport.cafe24.com/board/tip/read_begin.html?no=633&board_no=1002
    - 간단정리 https://kenna-hwa.tistory.com/116
- jQuery 버전 충돌 해결
    - https://sdsupport.cafe24.com/board/tip/read_begin.html?no=624&board_no=1002

## 스마트디자인 HTML/CSS 수정

### 브랜드 컬러 설정
1. index.html - layout.html - common.css
2. :root 블럭에 CSS 변수 설정
3. 파일들 열어서 #zzzzzz 를 var(--color-var) 로 변경

### 하단 로고 별도 설정
1. index.html - layout.html - footer.html
2. layout_logobottom 에서 로고 변경
    - 스마트디자인 창으로 변경이 안 됨
    - 임시로 → 상단에 있는 모듈을 옮겨서 수정하면 스마트디자인 gui로 이미지 업로드 가능함

### 스마트 배너 추가할 때 가로 full
- \<section\> class에 section_full 추가
- 예시
    ```html
    <div app4you-smart-banner="smart-banner-admin-RES00001" 
        app4you-smart-banner-html="true" 
        class="xans-element- xans-smart-banner-admin xans-smart-banner-admin-RES00001 section section_full" 
        data-ez="module-0ffmp1c-1" 
        data-ez-layoutsize="full" 
        data-ez-size-pc="1920 800" 
        data-ez-size-mobile="720 915" 
        data-ez-banner-area-no="947364" 
        style="--pc-width: 1920px; --pc-height: 800px; --mobile-width: 720px; --mobile-height: 915px;">
    ```

### 스마트 팝업
- slider type, 일반 type 모두 대응 가능하도록 조정
- index.html - main.css
    ```css
    /* 스마트 팝업 (PC/모바일 공통) */
    .app-smart-popup { 
        position:fixed !important; 
        overflow:hidden; 
        transform:translate(-50%, -50%); 
        width:100%; 
        height:100%;
        display:flex; 
        flex-direction:column; 
        align-items:center; 
        justify-content:center; 
        background:rgba(0,0,0,.4); 
        top:50% !important; 
        left:50% !important; 
        margin:0 !important; 
        border:0 !important; 
    }
    .app-smart-popup > .app-smart-popup-slider,
    .app-smart-popup > div > .smart-popup-img { 
        position:relative; 
        overflow:hidden; 
        border-radius:2vw; 
        max-width:98vw; 
        background-color:unset !important; 
    }
    .app-smart-popup > .app-smart-popup-slider img,
    .app-smart-popup > div > .smart-popup-img img { 
        max-width:98vw !important; 
    }
    .app-smart-popup > .smart-popup-btns { 
        display:flex; 
        border-radius:0; 
        border:0 !important; 
        background-color:unset !important; 
    }
    .app-smart-popup > .smart-popup-btns button { 
        border:0 !important; 
        color:#fff !important; 
        background-color:unset !important; 
        min-width:150px; 
        padding:13px 0;
    }
    .app-smart-popup > .smart-popup-btns button:first-child { 
        text-align:left; 
        margin-left:20px; 
    }
    .app-smart-popup > .smart-popup-btns button:last-child { 
        text-align:right; 
        margin-right:20px; 
    }
    ```

### 인스타그램 위젯 - snapwidget
- 사전 설정
    - https://snapwidget.com 에 가입하고
    - instagram grid (free) 에서
    - instagram channel connect
    - 반응형 디자인을 위해 PC는 6x2 grid, mobile은 3x4 grid
- index.html
    ```html
    <section class="section" data-ez-module="html/1" data-ez-name="CUSTOM HTML" data-ez-type="plain" data-ez="contents-0lvh4es-1" style="margin-bottom:120px;">
        <div class="main_title ez-align-left" data-ez-role="ez-align" data-ez-align="left" style="margin-bottom:30px;">
            <!-- 온라인 타이틀 수정하는곳 -->
            <div class="main_title_txt01" data-ez-role="title">인스타그램</div>
            <div class="main_title_txt02" data-ez-role="subtitle">인스타그램에서 델리쉬프룻을 만나보세요.</div>
        </div>
        <!-- SnapWidget -->
        <script src="https://snapwidget.com/js/snapwidget.js"></script>
        <iframe src="https://snapwidget.com/embed/1086436" class="snapwidget-widget pc" allowtransparency="true" frameborder="0" scrolling="no" style="border:none; overflow:hidden;  width:100%; "></iframe>
        <iframe src="https://snapwidget.com/embed/1086447" class="snapwidget-widget mobile" allowtransparency="true" frameborder="0" scrolling="no" style="border:none; overflow:hidden;  width:100%; "></iframe>
    </section>
    ```
- CSS
    - index.html - main.css
    ```css
    .snapwidget-widget.pc { display:block;}
    .snapwidget-widget.mobile { display:none;}
    @media all and (max-width:1024px) { 
        .snapwidget-widget.pc { display:none;}
        .snapwidget-widget.mobile { display:block;}
    }
    ```
- CSS (from 스마트디자인 Easy)
    ```css
    .main_title.ez_align_left { text-align:left; }
    .main_title .main_title_txt01 { font-size:24px; font-weight:700; line-height:1; color:#3a3a3a; }
    .main_title .main_title_txt02 { font-size:16px; font-weight:400; line-height:1; color:#9a9a9a; margin-top:15px; }

    @media (max-width:1760px) {
        .main_title .main_title_txt01 { font-size: calc(18px + (24 - 18) * ((100vw - 370px) / (1760 - 370)));}
        .main_title .main_title_txt02 { font-size:calc(13px + (16 - 13) * ((100vw - 370px) / (1760 - 370))); }
    }

### 메인 페이지 - 리뷰 섹션
- 사전 설정
    - 게시판 관리 
        - 이미지 표시 `사용`
        - 이미지 리사이징 `1,000px 초과`
    - 갤러리 게시판
        - 목록이미지 리사이징 `1,000px`
- 스마트디자인 Easy - 커스텀 HTML 생성
- swiper script / grid5_slide layout
- 수정해야할 영역
    - \<section\> class에 main_review_slide
    - main_title_txt01 innerText - Review
    - main_title_txt02 innerText - 구매하신 분들의 소중한 리뷰
    - main_title_bar_between a link(href)
- 스마트디자인 모듈
    - `{$img_src}`
    - 리뷰 사진(첨부파일 이미지)을 고퀄로 바꾸려면 `/file_data/카페24id{$real_filename}`
    - 안되면 `//ecimg.cafe24img.com/개별코드/카페24id/file_data{$real_filename}`
        - 예시 //ecimg.cafe24img.com/pg1422b79791670073/apples1917/file_data{$real_filename}
- index.html
    ```html
    <section class="section main_review_slide" data-ez-module="html/1" data-ez-name="CUSTOM HTML" data-ez-type="plain" data-ez="contents-1f2cw3u-1">
        <div class="main_title ez-align-left" data-ez-role="ez-align" data-ez-align="left"><!-- 타이틀 수정하는곳 -->
            <div class="main_title_txt01" data-ez-role="title">Review</div>
            <div class="main_title_bar_between"><div class="main_title_txt02 ellipsis-text" data-ez-role="subtitle">구매하신 분들의 소중한 리뷰</div><a href="/board/%EB%A6%AC%EB%B7%B0/4/">전체보기 &gt;</a></div>
        </div><!-- //main_title -->
        <div class="swiper-container main_review" module="board_listpackage_4">
            <ul class="swiper-wrapper grid5_slide" module="board_list_4">
                <!--
                    $count = 8
                    $main_list = yes
                    $subject_cut = 100
                    $content_cut = 100
                    $main_list_reply_view = no
                -->
                <li class="swiper-slide {$block_target_class}" {$block_data_attr}="">
                    <div class="thumbnail">
                        <a href="{$link_product_detail}" class="{$block_content_class}"><img src="//ecimg.cafe24img.com/pg1422b79791670073/applestore1917/file_data{$real_filename}" onerror="this.src='{$product_img_src}'" alt="" loading="lazy" ez-prevent="img"></a>
                    </div>
                    <div class="description">
                        <a href="{$link_product_detail}" class="{$block_content_class}"><span class="title ellipsis-text">{$subject|cut:40,..}</span>
                            <p><img src="//img.echosting.cafe24.com/skin/skin/board/icon-star-rating{$point_count}.svg" alt="{$point_count}점"> <span>{$writer}</span></p>
                            <span class="content">{$content|striptag}</span></a>
                    </div>
                </li>
                <li class="swiper-slide {$block_target_class}" {$block_data_attr}="">
                    <div class="thumbnail">
                        <a href="{$link_product_detail}" class="{$block_content_class}"><img src="{$img_src}" onerror="this.src='{$product_img_src}'" alt="" loading="lazy" ez-prevent="img"></a>
                    </div>
                    <div class="description">
                        <a href="{$link_product_detail}" class="{$block_content_class}"><span class="title ellipsis-text">{$subject|cut:40,..}</span>
                            <p><img src="//img.echosting.cafe24.com/skin/skin/board/icon-star-rating{$point_count}.svg" alt="{$point_count}점"> <span>{$writer}</span></p>
                            <span class="content">{$content|striptag}</span></a>
                    </div>
                </li>
            </ul>
        </div>
        <div class="swiper-prev"></div>
        <div class="swiper-next"></div>
    </section>
    ```
- CSS
    - index.html - main.css
    ```css
    .main_title .main_title_bar_between { display:flex; flex-direction:row; align-items:center; justify-content:space-between; }
    /* 리뷰 섹션 */
    .main_review_slide .main_review { padding:0 0 30px 0; margin:22px 0 0; }
    .main_review_slide .main_review ul { display:flex; }
    .main_review_slide .main_review ul > li { display:flex; flex-direction:column; }
    .main_review_slide .main_review ul.grid3_slide > li { flex-basis:27%; }
    .main_review_slide .main_review ul.grid4_slide > li { flex-basis:21%; }
    .main_review_slide .main_review ul.grid5_slide > li { flex-basis:17%; }
    .main_review_slide .main_review ul > li > .thumbnail { width:100%; aspect-ratio:1; overflow:hidden; position:relative; }
    .main_review_slide .main_review ul > li > .thumbnail img { width:100%; height:100%; object-fit:cover; position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); }
    .main_review_slide .main_review ul > li > .description { margin:15px auto 0; width:95%; }
    .main_review_slide .main_review ul > li > .description a { font-size:.9rem; line-height:1.2; }
    .main_review_slide .main_review ul > li > .description a > span.title { display:block; width:100%; }
    .main_review_slide .main_review ul > li > .description a > p { display:flex; justify-content:space-between; margin:10px 0; }
    .main_review_slide .main_review ul > li > .description a > p img { width:120px; height:auto; margin:0 -7px; filter:invert(82%) sepia(45%) saturate(2907%) hue-rotate(353deg) brightness(103%) contrast(102%); }
    .main_review_slide .main_review ul > li > .description a > p img.ec-common-rwd-image { vertical-align:baseline; }
    .main_review_slide .main_review ul > li > .description a > span.content { color:#aaa; overflow:hidden; text-overflow:ellipsis; word-wrap:break-word; line-height:1.2rem; display:-webkit-box; -webkit-line-clamp:4; -webkit-box-orient:vertical; }
    ```
- JS
    - index.html - main.js
    ```js
	/* 리뷰 슬라이드 */
	var review_slide = new Swiper('.main_review_slide .main_review', {
		slidesPerView: 'auto',
		spaceBetween: 20,
		observer: true,
		observeParents: true,
		speed: 700,
		watchOverflow: 'true',
		preloadImages: false,
        loop: true,
		lazy : {
			loadPrevNext : true,
		},
		scrollbar: {
			el: ".swiper-scrollbar",
			hide: false,
			draggable: true,
		},
		navigation: {
			nextEl: '.main_review_slide .swiper-next',
			prevEl: '.main_review_slide .swiper-prev',
		},
		autoplay: {
			delay: 2000,
			disableOnInteraction: false,
		},
		breakpoints: {
			768: {
				slidesPerView: 'auto',
				spaceBetween: 10,
			},
		}
	});
    ```

### 상품 상세보기 내 리뷰 섹션 커스텀
- 

### 공지사항 등 게시판
- 이미지 갤러리 형식으로 메인으로 가져오기

### 게시판 페이지 커스텀
- 공지사항은 커스텀 불필요
- 갤러리 게시판은 이미지 사이즈 작게 나오는지 확인
- 상품 후기 게시판은 상품으로만 접근하도록 해야 함
    - 할 일이 너무 많음...



### 카페24 메뉴얼
http://1004web.kr/board_HJSp58/7922

### 스마트디자인-PC-쇼핑몰에서의-금액-표시-관련-디자인-적용-TIP
https://support.cafe24.com/hc/ko/articles/8469490444441
