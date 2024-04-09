# 구현 내용

터보레포를 활용한 모노레포 구축

모노레포의 폴더 구조와 환경 설정에 대한 이해를 가지기 위해서 실습해봤습니다!

# 터보레포 란



### 모노레포란?
두 개 이상의 프로젝트 코드를 하나의 버전 관리 저장소(repository)에서 관리하는 방법

![](https://velog.velcdn.com/images/hyunjoong/post/e91b296a-dabd-4045-bc5a-b9b0cca92011/image.png)
출처: https://levelup.gitconnected.com/moving-from-multiple-repositories-to-a-lerna-js-mono-repo-faa97aeee35b

# Turborepo의 특징

![](https://velog.velcdn.com/images/hyunjoong/post/5b3902c5-028c-408d-af2b-f7ec41f81501/image.png)
## 1. Incremental builds
- 사용자가 빌드한 내용을 기억하고 이미 계산한 내용은 건너뛴다.

```typescript
> pnpm run build
```
![](https://velog.velcdn.com/images/hyunjoong/post/79604320-c6d5-4bcf-b218-a50492fe0041/image.png)
## 2. Content-aware hashing
타임스탬프가 아닌 파일의 내용을 파악하는 것으로 빌드할 항목을 확인한다. 따라서 변경된 파일만 빌드할 수 있다.

## 3. Parallel execution
모든 코어를 사용하여 최대한 병렬 처리를 하여 작업을 진행한다.


## 4. Remote Caching
빌드 파일을 remote에 캐싱해서 팀원 및 CI/CD와 원격 빌드 캐시를 공유한다.
## 5. Zero runtime overhead
런타임 코드와 소스 맵을 다루지 않는다.

## 6. Pruned subsets
빌드에 필요한 요소만으로 모노레포의 하위 집합을 생성해 PaaS 배포 속도를 높인다.
# 구현한 저장소

https://github.com/hyjoong/turbo

# 참고

- https://turbo.build/
