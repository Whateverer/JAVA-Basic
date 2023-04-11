# JAVA-Basic

## Enum
내가 만든 Enum
```java
package kr.exotech.dsfood.web.memo;

import lombok.AllArgsConstructor;
import lombok.Getter;
import org.apache.poi.ss.formula.functions.T;

import java.util.Arrays;
import java.util.List;


@AllArgsConstructor
@Getter
public enum MemoUseEnum {
    /*RESULT_RESULT("배식현황", "dms_meal_result", 1),
    RESULT_UNCARD("배식현황", "dms_meal_result_uncard", 2),
    APPLY_ORDER("급식신청관리", "dms_meal_order", 3),
    APPLY_UNPAY("급식신청관리", "dms_meal_order_unpay", 4),
    APPLY_MOD("급식신청관리", "dms_meal_order_mod", 5),
    CANCEL_CANCEL("급식환불관리", "dms_meal_order_cancl", 6),
    UNPAY_RESULT("미납비용관리", "dms_meal_result", 7),
    STATS_ORDER("매출통계", "dms_meal_order", 8),
    STATS_MOD("매출통계", "dms_meal_order_mod", 9),
    STATS_CANCEL("매출통계", "dms_meal_order_cancl", 10),
    STATS_UNPAY("매출통계", "dms_meal_order_unpay", 11);*/

    MEAL_RESULT("배식현황", Arrays.asList(
            new MemoTable(1, "dms_meal_result"),
            new MemoTable(2, "dms_meal_result_uncard"))),
    MEAL_APPLY("급식신청관리", Arrays.asList(
            new MemoTable(3, "dms_meal_order"),
            new MemoTable(4, "dms_meal_order_unpay"),
            new MemoTable(5, "dms_meal_order_mod"))),
    MEAL_CANCEL("급식환불관리", Arrays.asList(new MemoTable(6, "dms_meal_order"))),
    MEAL_UNPAY("미납비용관리", Arrays.asList(new MemoTable(7, "dms_meal_result"))),
    MEAL_STATS("매출통계", Arrays.asList(
            new MemoTable(8, "dms_meal_order"),
            new MemoTable(9, "dms_meal_order_mod"),
            new MemoTable(10, "dms_meal_order_cancl"),
            new MemoTable(11, "dms_meal_order_unpay")))
    ;

    String pageNm;
    List<MemoTable> memoTables;

    public MemoTable getMemoTable(String tableNm) {
        for (MemoTable memoTable: memoTables) {
            if (tableNm.equals(memoTable.getTableNm())) return memoTable;
        }
        return null;
    }

    public int getMemoSeq (String tableNm) {
        for (MemoTable memoTable: memoTables) {
            if (tableNm.equals(memoTable.getTableNm())) return memoTable.getMemoSeq();
        }
        return 0;
    }
}
```
