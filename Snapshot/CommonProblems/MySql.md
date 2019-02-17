#MySql常见问题

**ONLY_FULL_GROUP_BY**

```mysql
SET GLOBAL sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));
SET sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));
```



```
  @Test
  public void test_doCommentUpdate_ok_05() throws Exception {
	// 認証済みにする
    this.setAuthentication("user", new String[] { "ROLE_1" });

    D20401FormBean d20401FormBean = new D20401FormBean();
    d20401FormBean.setUpdateDt(DateUtil.parseTimestamp("2018-09-06 18:53:02.000"));
    d20401FormBean.setApplicationDepartureDay(java.sql.Date.valueOf("2019-01-01"));
    
      Map<String, String[]> messageMap = new HashMap<String, String[]>();
      messageMap.put("INF00082", new String[] {"登録処理"});
      d20401FormBean.setMessageMap(messageMap);

    Router router = createRouter(d20401FormBean, D20401Controller.class.getSimpleName(), D20401Controller.PAGE_PATH);
    mockMvc
        // リクエストを請求する
        .perform(post(D20401Controller.BASIC_URL + "/commentUpdate").with(csrf())
            .sessionAttr(SysConst.PAGE_ROUTER, router).param("freedomDescriptiveUpFlag", "true")
            .param("staffFreedomDescriptiveUpFlag", "true").param("applicationOrder", "1")
            .param("handlingPlaceCd", "").param("placeCd", "02")
        .param("courseNo", "00L0011").param("preGamenId", "2")
        .param("applicationOrder", "1"))
        // HTTP ステータスがＯＫであること
        .andExpect(status().isOk());
  }
```

