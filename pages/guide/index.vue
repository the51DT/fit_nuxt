<template>
    <div>
        <div class="guide-content">
            <div class="font-body-md font-semibold">개요</div>
            <div class="guide-page__table-wrap mt-5">
            <table>
                <colgroup>
                <col style="width: 20%" />
                <col />
                </colgroup>
                <tbody id="info-table-body">
                <tr>
                    <th scope="row">프로젝트</th>
                    <td>{{ iaData?.siteName || '데이터 없음' }}</td>
                </tr>
                <tr>
                    <th scope="row">기간</th>
                    <td>{{ iaData?.period || '미정' }}</td>
                </tr>
                <tr>
                    <th scope="row">가이드 작업자</th>
                    <td>{{ iaData?.worker || '미정' }}</td>
                </tr>
                <tr>
                    <th scope="row">대표 이메일</th>
                    <td>{{ iaData?.email || '없음' }}</td>
                </tr>
                </tbody>
            </table>
            </div>
            <ul class="description-list">
            <li> 프로젝트 수행을 위한 기본 가이드를 제공한다.</li>
            </ul>
        </div>
    </div>
</template>
