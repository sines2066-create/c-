#include <stdio.h>
#include <stdlib.h>
#define PRODUCT_COUNT 5

typedef struct {
    int stock_in;
    int sold;
    int stock;
} Product;

void printMenu() {
    printf("\n=== 쇼핑몰 재고 관리 시스템 ===\n");
    printf("1. 입고\n");
    printf("2. 판매\n");
    printf("3. 상품 현황\n");
    printf("4. 프로그램 종료\n");
    printf("메뉴 선택 >> ");
}

void printStatus(Product products[]) {
    printf("\n[상품 현황]\n");
    printf("번호\t입고수량\t판매수량\t재고수량\n");
    for (int i = 0; i < PRODUCT_COUNT; i++) {
        printf("%d\t%d\t\t%d\t\t%d\n",
               i + 1,
               products[i].stock_in,
               products[i].sold,
               products[i].stock);
    }
}

int main() {
    Product products[PRODUCT_COUNT] = {0};
    int menu, num, aaa;

    while (1) {
        printMenu();
        scanf("%d", &menu);

        switch (menu) {
            case 1:
                printf("입고할 상품 번호 (1~%d): ", PRODUCT_COUNT);
                scanf("%d", &num);

                if (num < 1 || num > PRODUCT_COUNT) {
                    printf("잘못된 상품 번호입니다.\n");
                    break;
                }

                printf("입고 수량 입력: ");
                scanf("%d", &aaa);

                products[num - 1].stock_in += aaa;
                products[num - 1].stock += aaa;

                printf("상품 %d번에 %d개 입고 완료.\n", num, aaa);
                break;

            case 2:
                printf("판매할 상품 번호 (1~%d): ", PRODUCT_COUNT);
                scanf("%d", &num);

                if (num < 1 || num > PRODUCT_COUNT) {
                    printf("잘못된 상품 번호입니다.\n");
                    break;
                }

                printf("판매 수량 입력: ");
                scanf("%d", &aaa);

                if (products[num - 1].stock < aaa) {
                    printf("재고 부족! 현재 재고: %d개\n", products[num - 1].stock);
                } else {
                    products[num - 1].sold += aaa;
                    products[num - 1].stock -= aaa;

                    printf("상품 %d번 %d개 판매 완료.\n", num, aaa);
                }
                break;

            case 3:
                printStatus(products);
                break;

            case 4:
                printf("프로그램을 종료합니다.\n");
                exit(0);

            default:
                printf("잘못된 선택입니다.\n");
        }
    }

    return 0;
}
