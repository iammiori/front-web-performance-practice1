# 성능 개선 보고서

<a href="https://d36tutom3ehed0.cloudfront.net/" target="_blank">배포 URL (CloudFront)</a>


## Image Optimization: JPG to WebP Conversion

### Why WebP?

- 파일별 크기 감소율 (평균 -47.2 %)

| 이미지 | JPG/PNG | WebP | 감소율 |
|--------|---------|------|--------|
| Hero_Desktop | 1.1 MB (1,126.4 KB) | 634 KB | -43.7% |
| Hero_Mobile | 415 KB | 222 KB | -46.5% |
| Hero_Tablet | 788 KB | 441 KB | -44.0% |
| menu_icon | 125 byte | 70 byte | -44.0% |
| vr1 | 54 KB | 26 KB | -51.9% |
| vr2 | 91 KB | 44 KB | -51.6% |
| vr3 | 76 KB | 39 KB | -48.7% |


| 최적화 측면 | 상세 설명 |
|------------|----------|
| 💰 CDN 비용 절감 | • 더 작은 파일 크기로 인한 전송 비용 절감<br>• 캐시 효율성 증가 |
| 🚀 로딩 성능 | • 동일 화질 대비 25-34% 더 작은 파일 크기<br>• 페이지 로딩 속도 개선<br>• First Contentful Paint (FCP) 시간 단축 |
| 📱 모바일 최적화 | • 모바일 네트워크에서 더 빠른 로딩<br>• 데이터 사용량 감소 |
| 💎 화질 및 기능 | • 손실/무손실 압축 모두 지원<br>• 알파 채널(투명도) 지원 |

### 구현 시 고려사항
- 브라우저 호환성 이슈로 `<picture>` 태그 넣어줘서, WebP를 지원하지 않는 브라우저를 위한 폴백(fallback) 이미지도 함께 제공

### 결과
- 👍 Core Web Vitals 의 LCP 항목이 14.63s -> 9.63s 로 감소됨
- 👎 다만 아직 4s이상 소요되므로 더 개선 필요
