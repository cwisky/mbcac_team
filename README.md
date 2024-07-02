# mbcac_team

## 팀 프로젝트 안내
* 주제: 열심히 하자
* 기간: 3달
  + 1달: 분석
  + 1달: 설계
  + 1달: 구현
    - 1주: 로그인
    - 2주: 게시판
    - 3주: 뉴스

## 아래의 코드를 참고하세요
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
	<jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```
[github마크다운으로 색상 설정하기](https://gist.github.com/luigiMinardi/4574708d404cdf4fe0da7ac6fe2314db)
$\color{#ff0000}{\textsf{색상 설정}}$
