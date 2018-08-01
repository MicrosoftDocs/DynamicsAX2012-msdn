﻿---
title: X++ Grammar
TOCTitle: X++ Grammar
ms:assetid: 6ed6e25a-a9c0-4c94-ab2f-650828cef97f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd261486(v=AX.60)
ms:contentKeyID: 35244843
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Grammar [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic shows the formal grammar of the X++ language in Microsoft Dynamics AX.

## How to Interpret the Formal BNF Grammar

This section describes the grammar of X++ in Backus Naur Form (BNF). A small example of BNF is described here.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>BNF code</p></th>
<th><p>Interpretation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>AA ::= BB  CC_SYM
BB ::= JJ_SYM
   ::= KK_SYM</code></pre></td>
<td><p>AA is the name of a production rule.</p>
<p>An AA requires a BB, followed by a CC_SYM.</p>
<p>A BB is also a production rule. Therefore, BB is not a terminal.</p>
<p>BB must be either a JJ_SYM or a KK_SYM. Both JJ_SYM and KK_SYM are terminals because they are not the names of any other production rules. CC_SYM is also a terminal.</p></td>
</tr>
</tbody>
</table>

 

In the BNF for X++ grammar, most of the terminals have \_SYM as the suffix of their name.

## The Formal X++ Grammar in BNF

This section contains the BNF that defines the grammar of X++.

    CMPL_UNIT ::= RETTYPEID  FUNC_HDR  FUNC_HEAD  BODY
              ::= RETTYPEID  DATA_HDR  CLASS_DECL
              ::= EXPR_HDR  IF_EXPR  SEMIOPT
              ::= RETTYPEID  FUNC_HDR  EVENT_DECL  BODY
    
    SEMIOPT ::= SEMICOLON_SYM
            ::= 
    
    CLASS_DECL ::= CLASS_HEADER  LEFTBR_SYM  DCL_EVENTMAP  DCL_LIST  RIGHTBR_SYM
    
    CLASS_HEADER ::= ATTRIBUTE_DEF  CLASS_MODIFIERS  CLASSORINTERFACE  STD_ID  EXTENDS  IMPLEMENTS
    
    ATTRIBUTE_DEF ::= LEFT_BRKT_SYM  ATTRIBUTE_INIT  ATTRIBUTE_LIST  RETTYPEID  RGHT_BRKT_SYM
                  ::= 
    
    ATTRIBUTE_INIT ::= 
                   .
    
    ATTRIBUTE_LIST ::= ATTRIBUTE
                   ::= ATTRIBUTE_LIST  LIST_SEP_SYM  ATTRIBUTE
    
    ATTRIBUTE ::= STD_ID
              ::= ATTRIBUTE_WITH_ARGS_BEGINS  ATTRIBUTE_WITH_ARGS_ENDS
    
    ATTRIBUTE_WITH_ARGS_BEGINS ::= STD_ID  LEFT_PAR_SYM
    
    ATTRIBUTE_WITH_ARGS_ENDS ::= ATTRIBUTE_ARGS  RGHT_PAR_SYM
    
    ATTRIBUTE_ARGS ::= ATTRIBUTE_CONSTANT
                   ::= ATTRIBUTE_ARGS  LIST_SEP_SYM  ATTRIBUTE_CONSTANT
    
    ATTRIBUTE_CONSTANT ::= INT_SYM
                       ::= DBL_SYM
                       ::= STR_SYM
                       ::= DATE_SYM
                       ::= DATETIME_SYM
                       ::= STD_ID  DBLCOLON_SYM  STD_ID
                       ::= TRUE_SYM
                       ::= FALSE_SYM
                       ::= INT64_SYM
                       ::= ATTRIBUTE_INTRINSIC
    
    ATTRIBUTE_INTRINSIC ::= INTRI_ID  LEFT_PAR_SYM  IARGS  RGHT_PAR_SYM
    
    CLASSORINTERFACE ::= CLASS_SYM
                     ::= INTERFACE_SYM
    
    CLASS_MODIFIERS ::= CLASS_MODS
                    ::= 
    
    CLASS_MODS ::= CLASS_MODIFIER
               ::= CLASS_MODS  RETTYPEID  CLASS_MODIFIER
    
    CLASS_MODIFIER ::= PUBLIC_SYM
                   ::= FINAL_SYM
                   ::= STATIC_SYM
                   ::= ABSTRACT_SYM
                   ::= PRIVATE_SYM
    
    EXTENDS ::= EXTENDS_SYM  STD_ID
            ::= 
    
    IMPLEMENTS ::= IMPLEMENTS_SYM  IMPLEMENTLIST
               ::= 
    
    IMPLEMENTLIST ::= STD_ID
                  ::= IMPLEMENTLIST  LIST_SEP_SYM  STD_ID
    
    DCL_EVENTMAP ::= 
    
    EVENT_DECL ::= ATTRIBUTE_DEF  EVENT_HEADER  PARM_DCL_LIST
    
    EVENT_HEADER ::= EVENT_MODIFIER  VOID_TYPE_SYM  STD_ID
    
    EVENT_MODIFIER ::= EVENT_SYM
    
    FUNC_HEAD ::= ATTRIBUTE_DEF  FUNCNAME  PARM_DCL_LIST
    
    FUNCNAME ::= FUNCTYPE  STD_ID
    
    FUNCTYPE ::= FUNC_MODIFIERS  DECL_TYPE
    
    FUNC_MODIFIERS ::= FUNC_MODS
                   ::= 
    
    FUNC_MODS ::= RETTYPEID  FUNC_MODIFIER
              ::= FUNC_MODS  RETTYPEID  FUNC_MODIFIER
    
    FUNC_MODIFIER ::= PUBLIC_SYM
                  ::= PRIVATE_SYM
                  ::= PROTECTED_SYM
                  ::= FINAL_SYM
                  ::= STATIC_SYM
                  ::= ABSTRACT_SYM
                  ::= DISPLAY_SYM
                  ::= EDIT_SYM
                  ::= SERVER_SYM
                  ::= CLIENT_SYM
    
    BODY ::= LEFTBR_SYM  DCL_FUNC_LIST  SEMIOPT  SECAUTHZCHECK  STMTLIST  SECAUTHZEND  RIGHTBR_SYM
    
    SECAUTHZCHECK ::= 
    
    SECAUTHZEND ::= 
    
    RETTYPEID ::= 
    
    FUNCTION_DEF ::= FUNC_HEADER  PARM_DCL_LIST  LOCAL_BODY
    
    FUNC_HEADER ::= DECL_TYPE  STD_ID
    
    PARM_DCL_LIST ::= RETTYPEID  PARM_START  PARM_LIST_OPT  RGHT_PAR_SYM  RETTYPEID
    
    PARM_START ::= LEFT_PAR_SYM
    
    PARM_LIST_OPT ::= PARM_LIST
                  ::= 
    
    PARM_LIST ::= DCL_INIT
              ::= PARM_LIST  LIST_SEP_SYM  DCL_INIT
    
    LOCAL_BODY ::= LEFTBR_SYM  DCL_LIST  SEMIOPT  STMTLIST  RETTYPEID  RIGHTBR_SYM
    
    DCL_LIST ::= DCL_LIST2
             ::= 
    
    DCL_LIST2 ::= DCL_STMT
              ::= DCL_LIST2  DCL_STMT
    
    DCL_FUNC_LIST ::= DCL_FUNC_LIST2
                  ::= 
    
    DCL_FUNC_LIST2 ::= DCL_STMT
                   ::= FUNCTION_DEF
                   ::= DCL_FUNC_LIST2  DCL_STMT
                   ::= DCL_FUNC_LIST2  FUNCTION_DEF
    
    DCL_STMT ::= DCL_INIT_LIST  RETTYPEID  SEMICOLON_SYM
    
    DCL_INIT_LIST ::= DCL_INIT
                  ::= DCL_CLIST  ASG_CLAUSE
    
    DCL_CLIST ::= DCL_INIT_LIST  LIST_SEP_SYM  STD_ID  ARR_DCL_IDX
    
    DCL_INIT ::= DECL  ASG_CLAUSE
    
    DECL ::= DECL_TYPE  STD_ID  ARR_DCL_IDX
    
    DECL_TYPE ::= STR_TYPE_SYM  STR_LEN
              ::= INT_TYPE_SYM
              ::= DBL_TYPE_SYM
              ::= DATE_TYPE_SYM
              ::= DATETIME_TYPE_SYM
              ::= TYPE_ID
              ::= QUEUE_TYPE_SYM
              ::= VOID_TYPE_SYM
              ::= ANY_TYPE_SYM
              ::= GUID_TYPE_SYM
              ::= INT64_TYPE_SYM
              ::= CLR_TYPE
    
    CLR_TYPE ::= CLR_NAMESPACE  TYPE_ID  CLR_ARRAY_TYPE_EXT
             ::= CLR_NAMESPACE  CLR_TYPE
    
    CLR_NAMESPACE ::= TYPE_ID  PERIOD_SYM
    
    CLR_ARRAY_TYPE_EXT ::= CLR_ARRAY_SPEC
                       ::= 
    
    CLR_ARRAY_SPEC ::= CLR_ARRAY_PART
                   ::= CLR_ARRAY_SPEC  CLR_ARRAY_PART
    
    CLR_ARRAY_PART ::= CLR_ARRAY_LEFT_PART  CLR_RECTANGULAR_LIST  RGHT_BRKT_SYM
    
    CLR_ARRAY_LEFT_PART ::= LEFT_BRKT_SYM
    
    CLR_RECTANGULAR_LIST ::= CLR_COMMA_LIST
                         ::= 
    
    CLR_COMMA_LIST ::= LIST_SEP_SYM
                   ::= CLR_COMMA_LIST  LIST_SEP_SYM
    
    STR_LEN ::= INT_SYM
            ::= 
    
    ARR_DCL_IDX ::= LEFT_BRKT_SYM  RANGE  ARRAY_MEM  RGHT_BRKT_SYM
                ::= 
    
    RANGE ::= IF_EXPR
          ::= 
    
    ARRAY_MEM ::= LIST_SEP_SYM  IF_EXPR
              ::= 
    
    ASG_CLAUSE ::= INIT_START  IF_EXPR
               ::= 
    
    INIT_START ::= ASG_SYM
    
    ASG_STMT ::= LVAL_FLD  ASSIGN  IF_EXPR
             ::= LVAL_LIST  ASG_SYM  IF_EXPR
             ::= LVAL_FLD  ASG_INC_DEC
             ::= ASG_INC_DEC  LVAL_FLD
             ::= LVAL_FLD  ASG_EVENT_HANDLER
    
    ASSIGN ::= ASG_SYM
           ::= ASGINC_SYM
           ::= ASGDEC_SYM
    
    ASG_INCDEC ::= ASGINC_SYM
               ::= ASGDEC_SYM
    
    ASG_EVENT_HANDLER ::= ASG_INCDEC  EVENTHANDLER_SYM  LEFT_PAR_SYM  QUALIFIER  STD_ID  RGHT_PAR_SYM
      ::= ASG_INCDEC  EVENTHANDLER_SYM  LEFT_PAR_SYM  STD_ID  DBLCOLON_SYM  STD_ID  RGHT_PAR_SYM
      ::= ASG_INCDEC  EVENTHANDLER_SYM  LEFT_PAR_SYM  QUALIFIER  EVAL_CLR_TYPE  DBLCOLON_SYM  STD_ID  RGHT_PAR_SYM
    
    ASG_INC_DEC ::= INC_SYM
                ::= DEC_SYM
    
    LVAL_FLD ::= FIELD
    
    LVAL_START ::= LEFT_BRKT_SYM
    
    LVAL_LIST ::= LVAL_START  LVALUES  RGHT_BRKT_SYM
    
    LVALUE ::= FIELD
    
    LVALUES ::= LVALUE
            ::= LVALUES  NEXTLVAL  LVALUE
    
    NEXTLVAL ::= LIST_SEP_SYM
    
    IF_EXPR ::= COND_TRUE  IF_EXPR
            ::= BOOL_EXPR
    
    COND_TRUE ::= COND_TEST  IF_EXPR  COLON_SYM
    
    COND_TEST ::= BOOL_EXPR  QUEST_SYM
    
    BOOL_EXPR ::= BOOL_EXPR  LOGOP  EXPR
              ::= EXPR
    
    LOGOP ::= AND_SYM
          ::= OR_SYM
    
    EXPR ::= SMPL_EXPR  RELOP  SMPL_EXPR
         ::= SMPL_EXPR  AS_SYM  STD_ID
         ::= SMPL_EXPR  IS_SYM  STD_ID
         ::= SMPL_EXPR  AS_SYM  EVAL_CLR_TYPE
         ::= SMPL_EXPR  IS_SYM  EVAL_CLR_TYPE
         ::= SMPL_EXPR
    
    RELOP ::= LT_SYM
          ::= LE_SYM
          ::= EQ_SYM
          ::= NE_SYM
          ::= GT_SYM
          ::= GE_SYM
          ::= LIKE_SYM
    
    SMPL_EXPR ::= SMPL_EXPR  ADDOP  TERM
              ::= TERM
    
    ADDOP ::= PLUS_SYM
          ::= MINUS_SYM
          ::= PHYSOR_SYM
    
    TERM ::= TERM  MULOP  CMPL_FACT
         ::= CMPL_FACT
    
    MULOP ::= MULT_SYM
          ::= DIV_SYM
          ::= MOD_SYM
          ::= INTDIV_SYM
          ::= SHIFTL_SYM
          ::= SHIFTR_SYM
          ::= PHYSAND_SYM
          ::= PHYSXOR_SYM
    
    CMPL_FACT ::= NOT_SYM  SGND_FACT
              ::= SGND_FACT
    
    SGND_FACT ::= SIGNOP  FACTOR
              ::= FACTOR
    
    SIGNOP ::= UMINUS_SYM
           ::= PHYSNOT_SYM
    
    FACTOR ::= LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM
           ::= CONSTANT
           ::= FIELD
           ::= DIRSEARCH
           ::= FUNCTION
           ::= INTRINSICS
           ::= EVAL
           ::= CONLITTERAL
           ::= NEW_CLR_ARRAY
    
    NEW_CLR_ARRAY ::= NEW_SYM  EVAL_CLR_TYPE  NEW_CLR_ARRAY_PART  LEFT_PAR_SYM  RGHT_PAR_SYM
    
    NEW_CLR_ARRAY_PART ::= CLR_SIZED_ARRAY  CLR_NOSIZED_ARRAY_SPEC
    
    CLR_SIZED_ARRAY ::= LEFT_BRKT_SYM  CLR_SMPL_EXPR_COMMA_LIST  RGHT_BRKT_SYM
    
    CLR_SMPL_EXPR_COMMA_LIST ::= SMPL_EXPR
      ::= CLR_SMPL_EXPR_COMMA_LIST  LIST_SEP_SYM  SMPL_EXPR
    
    CLR_NOSIZED_ARRAY_SPEC ::= CLR_NOSIZED_ARRAY_LIST
                           ::= 
    
    CLR_NOSIZED_ARRAY_LIST ::= CLR_NOSIZED_ARRAY
                           ::= CLR_NOSIZED_ARRAY_LIST  CLR_NOSIZED_ARRAY
    
    CLR_NOSIZED_ARRAY ::= LEFT_BRKT_SYM  CLR_EMPTY_COMMA_LIST  RGHT_BRKT_SYM
    
    CLR_EMPTY_COMMA_LIST ::= CLR_EMPTY_RECT_COMMA_LIST
                         ::= 
    
    CLR_EMPTY_RECT_COMMA_LIST ::= LIST_SEP_SYM
                              ::= CLR_EMPTY_RECT_COMMA_LIST  LIST_SEP_SYM
    
    CONLITTERAL ::= LEFT_BRKT_SYM  IF_EXPR  EXPR_LIST  RGHT_BRKT_SYM
    
    CONSTANT ::= INT_SYM
             ::= DBL_SYM
             ::= STR_SYM
             ::= DATE_SYM
             ::= DATETIME_SYM
             ::= STD_ID  DBLCOLON_SYM  STD_ID
             ::= TRUE_SYM
             ::= FALSE_SYM
             ::= NULL_SYM
             ::= INT64_SYM
             ::= QUALIFIER  EVAL_CLR_TYPE  DBLCOLON_SYM  STD_ID
             ::= QUALIFIER  STD_ID  DBLCOLON_SYM  STD_ID
    
    DIRSEARCH ::= DIRS_HEADER  PERIOD_SYM  STD_ID  ARR_IDX
              ::= DIRS_HEADER  PERIOD_SYM  FLD_NUM  ARR_IDX
    
    
    DIRS_HEADER ::= LEFT_PAR_SYM  SET_DIRS  FIND_JOIN  RGHT_PAR_SYM
    
    SET_DIRS ::= 
    
    FIELD ::= QUALIFIER  STD_ID  ARR_IDX
          ::= QUALIFIER  FLD_NUM  ARR_IDX
          ::= STD_ID  ARR_IDX
    
    QUALIFIER ::= EVAL  PERIOD_SYM
              ::= STD_ID  PERIOD_SYM
    
    FLD_NUM ::= LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM
    
    ARR_IDX ::= LEFT_BRKT_SYM  SMPL_EXPR  RGHT_BRKT_SYM
            ::= 
    
    EXPR_LIST ::= EXPR_LIST2
              ::= 
    
    EXPR_LIST2 ::= LIST_SEP_SYM  IF_EXPR
               ::= EXPR_LIST2  LIST_SEP_SYM  IF_EXPR
    
    FUNCTION ::= FUNC_ID  LEFT_PAR_SYM  EVAL_FUNCTION_NAME  PAR_LIST  RGHT_PAR_SYM
    
    EVAL_FUNCTION_NAME ::= 
    
    EVAL_NAME ::= EVAL_ID  LEFT_PAR_SYM
              ::= STD_ID  LEFT_PAR_SYM
              ::= STD_ID  DBLCOLON_SYM  STD_ID  LEFT_PAR_SYM
              ::= SUPER_SYM  LEFT_PAR_SYM
              ::= NEW_SYM  STD_ID  LEFT_PAR_SYM
              ::= NEW_SYM  EVAL_CLR_TYPE  LEFT_PAR_SYM
              ::= QUALIFIER  EVAL_CLR_TYPE  DBLCOLON_SYM  STD_ID  LEFT_PAR_SYM
              ::= QUALIFIER  STD_ID  LEFT_PAR_SYM
              ::= QUALIFIER  STD_ID  DBLCOLON_SYM  STD_ID  LEFT_PAR_SYM
    
    EVAL_CLR_TYPE ::= NAMESPACE  STD_ID
                  ::= NAMESPACE  EVAL_CLR_TYPE
    
    NAMESPACE ::= STD_ID  PERIOD_SYM
    
    EVAL ::= EVAL_NAME  PAR_LIST  RGHT_PAR_SYM
    
    PAR_LIST ::= PRM_LIST
             ::= 
    
    PRM_LIST ::= PAR_ELEM
             ::= PRM_LIST  LIST_SEP_SYM  PAR_ELEM
    
    PAR_ELEM ::= IF_EXPR
             ::= BYREF_SYM  FIELD
    
    INTRINSICS ::= INTRI_ID  LEFT_PAR_SYM  IARGS  RGHT_PAR_SYM
    
    IARGS ::= STD_ID
          ::= STR_SYM
          ::= STD_ID  LIST_SEP_SYM  STD_ID
          ::= 
    
    STMTLIST ::= STATEMENTS
             ::= 
    
    STATEMENTS ::= STATEMENT
               ::= STATEMENTS  STATEMENT
    
    STATEMENT ::= COMPOUND_STMT
              ::= WHILE_STMT
              ::= FOR_STMT
              ::= DO_STMT
              ::= SEARCH_STMT
              ::= FIND_STMT
              ::= PRINT_STMT
              ::= WINDOW_STMT
              ::= IF_STMT
              ::= SWITCH_STMT
              ::= EXPR_STMT
              ::= PAUSE_STMT
              ::= BP_CLAUSE
              ::= BREAK_STMT
              ::= CONTINUE_STMT
              ::= RETURN_CLAUSE
              ::= MOVE_REC_STMT
              ::= THROW_STMT
              ::= TRY_STMT
              ::= RETRY_STMT
              ::= TTS_STMT
              ::= FLUSH_STMT
              ::= TBLLOCK_STMT
              ::= CHANGE_STMT
              ::= UPDATE_STMT
              ::= INSERT_STMT
              ::= UNCHECKED_STMT
    
    COMPOUND_STMT ::= LEFTBR_SYM  STMTLIST  RIGHTBR_SYM
    
    THROW_STMT ::= THROW_SYM  IF_EXPR  SEMICOLON_SYM
    
    TRY_STMT ::= TRY_BLOCK  CATCH_LIST
    
    TRY_BLOCK ::= TRY_START  STATEMENT
    
    TRY_START ::= TRY_SYM
    
    CATCH_LIST ::= CATCH_STMT
               ::= CATCH_LIST  CATCH_STMT
    
    CATCH_STMT ::= CATCH_EXPR  PRE_CATCH  STATEMENT  POST_CATCH
    
    CATCH_EXPR ::= CATCH_SYM  LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM
      ::= CATCH_SYM  LEFT_PAR_SYM  IF_EXPR  LIST_SEP_SYM  TABLEINSTANCE  RGHT_PAR_SYM
      ::= CATCH_SYM
    
    PRE_CATCH ::= 
    
    POST_CATCH ::= 
    
    TABLEINSTANCE ::= INSTANCENAME
    
    INSTANCENAME ::= QUALIFIER  STD_ID  ARR_IDX
                 ::= STD_ID  ARR_IDX
    
    RETRY_STMT ::= RETRY_SYM  SEMICOLON_SYM
    
    WHILE_STMT ::= WHILE_TEST  STATEMENT
    
    WHILE_TEST ::= WHILE  LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM
    
    WHILE ::= WHILE_SYM
    
    DO_STMT ::= DO_BODY  DO_TEST  SEMICOLON_SYM
    
    DO_BODY ::= DO_HEADER  STATEMENT
    
    DO_HEADER ::= DO_SYM
    
    DO_TEST ::= WHILE_SYM  LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM
    
    FOR_STMT ::= FOR_HEADER  STATEMENT
    
    FOR_HEADER ::= FOR_TEST  SEMICOLON_SYM  FOR_ASG  RGHT_PAR_SYM
    
    FOR_TEST ::= FOR_INIT  SEMICOLON_SYM  IF_EXPR
    
    FOR_INIT ::= FOR_SYM  LEFT_PAR_SYM  FOR_ASG
    
    FOR_ASG ::= LVAL_FLD  ASSIGN  IF_EXPR
            ::= LVAL_FLD  ASG_INC_DEC
            ::= ASG_INC_DEC  LVAL_FLD
    
    JOIN_LIST ::= JOIN_SPECS
              ::= 
    
    JOIN_SPECS ::= JOIN_SPEC
               ::= JOIN_SPECS  JOIN_SPEC
    
    JOIN_SPEC ::= JOIN_ORDER  WHERE  IF_EXPR
              ::= JOIN_ORDER
    
    JOIN_ORDER ::= JOIN_USING
               ::= JOIN_USING  ORDER_GROUP
    
    JOIN_USING ::= JOIN_CLAUSE  USING_INDEX  STD_ID
               ::= JOIN_CLAUSE  USING_INDEX  HINT_SYM  STD_ID
               ::= JOIN_CLAUSE
    
    JOIN_CLAUSE ::= OUTER  JOIN_SYM  SELECTOPT  TABLE
    
    OUTER ::= OUTER_SYM
          ::= EXISTS_SYM
          ::= NOTEXISTS_SYM
          ::= 
    
    SEARCH_STMT ::= SEARCH_JOIN  STATEMENT
    
    SEARCH_JOIN ::= SEARCH_WHERE  JOIN_LIST
    
    SEARCH_WHERE ::= SEARCH_ORDER  WHERE  IF_EXPR
                 ::= SEARCH_ORDER
    
    WHERE ::= WHERE_SYM
    
    SUM_ELEM ::= SUM_FUNC  LEFT_PAR_SYM  STD_ID  RGHT_PAR_SYM
    
    SUM_FUNC ::= SUM_SYM
             ::= AVG_SYM
             ::= CNT_SYM
             ::= MINOF_SYM
             ::= MAXOF_SYM
    
    SEARCH_ORDER ::= SEARCH_USING
                 ::= SEARCH_USING  ORDER_GROUP
    
    ORDER_GROUP ::= ORDERBY_CLAUSE  OPT_GROUPBY
                ::= GROUPBY_CLAUSE  OPT_ORDERBY
    
    OPT_GROUPBY ::= GROUPBY_CLAUSE
                ::= 
    
    OPT_ORDERBY ::= ORDERBY_CLAUSE
                ::= 
    
    ORDERBY_CLAUSE ::= ORDER_SYM  OPT_BY  ORDER_ELEM
                   ::= ORDERBY_CLAUSE  LIST_SEP_SYM  ORDER_ELEM
    
    GROUPBY_CLAUSE ::= GROUP_SYM  OPT_BY  ORDER_ELEM
                   ::= GROUPBY_CLAUSE  LIST_SEP_SYM  ORDER_ELEM
    
    ORDER_ELEM ::= STD_ID  INDEX  DIRECTION
               ::= ORDER_QUALIFIER  STD_ID  INDEX  DIRECTION
    
    ORDER_QUALIFIER ::= STD_ID  PERIOD_SYM
    
    INDEX ::= LEFT_BRKT_SYM  INT_SYM  RGHT_BRKT_SYM
          ::= 
    
    DIRECTION ::= ASCEND_SYM
              ::= DESCEND_SYM
              ::= 
    
    OPT_BY ::= BY_SYM
           ::= 
    
    SEARCH_USING ::= SEARCH_CLAUSE  USING_INDEX  STD_ID
                 ::= SEARCH_CLAUSE  USING_INDEX  HINT_SYM  STD_ID
                 ::= SEARCH_CLAUSE
    
    USING_INDEX ::= INDEX_SYM
    
    SEARCH_CLAUSE ::= WHILE_SYM  SELECT_SYM  SELECTOPT  CROSSCOMPANY_CLAUSE  VALIDTIMESTATE_CLAUSE  TABLE
    
    CROSSCOMPANY_CLAUSE ::= CROSSCOMPANY_SYM
                        ::= CROSSCOMPANY_SYM  COLON_SYM  STD_ID
                        ::= 
    
    VALIDTIMESTATE_CLAUSE ::= VALIDTIMESTATE_SYM  LEFT_PAR_SYM  STD_ID  LIST_SEP_SYM  STD_ID  RGHT_PAR_SYM
      ::= VALIDTIMESTATE_SYM  LEFT_PAR_SYM  STD_ID  RGHT_PAR_SYM
      ::= 
    
    SELECTOPT ::= 
              ::= SELECTOPT  REVERSE_SYM
              ::= SELECTOPT  FIRSTFAST_SYM
              ::= SELECTOPT  FIRSTONLY_SYM
              ::= SELECTOPT  FIRSTONLY_SYM1
              ::= SELECTOPT  FIRSTONLY_SYM10
              ::= SELECTOPT  FIRSTONLY_SYM100
              ::= SELECTOPT  FIRSTONLY_SYM1000
              ::= SELECTOPT  FORUPDATE_SYM
              ::= SELECTOPT  NOFETCH_SYM
              ::= SELECTOPT  FORCE_SELECT_ORDER_SYM
              ::= SELECTOPT  FORCE_NESTED_LOOP_SYM
              ::= SELECTOPT  FORCE_LITERALS_SYM
              ::= SELECTOPT  FORCE_PLACEHOLDERS_SYM
              ::= SELECTOPT  REPEATABLEREAD_SYM
              ::= SELECTOPT  OPTIMISTICLOCK_SYM
              ::= SELECTOPT  PESSIMISTICLOCK_SYM
              ::= SELECTOPT  GENERATEONLY_SYM
    
    FIND_STMT ::= FIND_JOIN  SEMICOLON_SYM
    
    FIND_JOIN ::= FIND_WHERE  JOIN_LIST
    
    FIND_WHERE ::= FIND_ORDER  WHERE  IF_EXPR
               ::= FIND_ORDER
    
    FIND_ORDER ::= FIND_USING
               ::= FIND_USING  ORDER_GROUP
    
    FIND_USING ::= FIND_TABLE  USING_INDEX  STD_ID
               ::= FIND_TABLE  USING_INDEX  HINT_SYM  STD_ID
               ::= FIND_TABLE
    
    FIND_TABLE ::= SELECT_SYM  SELECTOPT  CROSSCOMPANY_CLAUSE  VALIDTIMESTATE_CLAUSE  TABLE
      ::= DELETE_SYM  SELECTOPT  CROSSCOMPANY_CLAUSE  VALIDTIMESTATE_CLAUSE  TABLE
    
    TABLE ::= FLD_LIST  OPT_FROM
    
    FLD_LIST ::= MULT_SYM
             ::= FIELD_LIST
    
    FIELD_LIST ::= FIELD_SPEC
               ::= FIELD_LIST  LIST_SEP_SYM  FIELD_SPEC
    
    FIELD_SPEC ::= STD_ID  INDEX
               ::= SUM_ELEM
    
    OPT_FROM ::= FROM_SYM  STD_ID
             ::= 
    
    SETFIELDSMODE ::= 
    
    UPDATE_STMT ::= UPDATETABLE  SET_SYM  SETFIELDSMODE  FIELDASSIGNMENTS  OPT_WHERE  JOIN_LIST  SEMICOLON_SYM
    
    UPDATETABLE ::= UPDATE_SYM  SELECTOPT  CROSSCOMPANY_CLAUSE  STD_ID
    
    OPT_WHERE ::= WHERE  IF_EXPR
              ::= 
    
    FIELDASSIGNMENTS ::= FIELDASSIGNMENTS  LIST_SEP_SYM  FIELDASSIGNMENT
                     ::= FIELDASSIGNMENT
    
    FIELDASSIGNMENT ::= STD_ID  INDEX  ASG_SYM  IF_EXPR
    
    INSERT_PART ::= INSERT_SYM  CROSSCOMPANY_CLAUSE  INSERT_NAME  LEFT_PAR_SYM  INSERTFIELDLIST  RGHT_PAR_SYM
    
    INSERT_NAME ::= STD_ID
    
    INSERT_STMT ::= INSERT_PART  FIND_JOIN  SEMICOLON_SYM
    
    INSERTFIELDLIST ::= INSERTFIELD
                    ::= INSERTFIELDLIST  LIST_SEP_SYM  INSERTFIELD
    
    INSERTFIELD ::= STD_ID  INDEX
    
    PRINT_STMT ::= PRINT_CLAUSE  AT_CLAUSE  SEMICOLON_SYM
    
    PRINT_CLAUSE ::= PRINT  IF_EXPR  EXPR_LIST
    
    PRINT ::= PRINT_SYM
    
    AT_CLAUSE ::= AT_SYM  IF_EXPR  LIST_SEP_SYM  IF_EXPR
              ::= 
    
    WINDOW_STMT ::= WINDOW_SYM  IF_EXPR  LIST_SEP_SYM  IF_EXPR  AT_CLAUSE  SEMICOLON_SYM
    
    IF_STMT ::= ELSE_STMT
            ::= IF_CONDS
    
    IF_CONDS ::= IF_COND  STATEMENT
    
    IF_COND ::= IF_SYM  LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM
    
    ELSE_STMT ::= ELSE  STATEMENT
    
    ELSE ::= IF_CONDS  ELSE_SYM
    
    SWITCH_STMT ::= CASE_LIST  RIGHTBR_SYM
    
    CASE_LIST ::= SWITCH_SYM  LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM  LEFTBR_SYM
              ::= CASE_TESTS  STMTLIST
    
    CASE_TESTS ::= CASE_HEADER  COLON_SYM
               ::= CASE_LIST  DEFAULT_SYM  COLON_SYM
    
    CASE_HEADER ::= CASE  IF_EXPR
                ::= CASEALT  IF_EXPR
    
    CASE ::= CASE_LIST  CASE_SYM
    
    CASEALT ::= CASE_HEADER  LIST_SEP_SYM
    
    EXPR_STMT ::= ASG_STMT  SEMICOLON_SYM
              ::= FUNCTION  SEMICOLON_SYM
              ::= INTRINSICS  SEMICOLON_SYM
              ::= EVAL  SEMICOLON_SYM
    
    PAUSE_STMT ::= PAUSE_SYM  SEMICOLON_SYM
    
    BP_CLAUSE ::= BP_SYM  SEMICOLON_SYM
    
    BREAK_STMT ::= BREAK_SYM  SEMICOLON_SYM
    
    CONTINUE_STMT ::= CONTINUE_SYM  SEMICOLON_SYM
    
    RETURN_CLAUSE ::= RETURN_SYM  SEMICOLON_SYM
                  ::= RETURN_SYM  IF_EXPR  SEMICOLON_SYM
    
    TTS_STMT ::= TTSABORT_SYM  SEMICOLON_SYM
             ::= TTSBEGIN_SYM  SEMICOLON_SYM
             ::= TTSEND_SYM  SEMICOLON_SYM
    
    FLUSH_STMT ::= FLUSH  ID_LIST  SEMICOLON_SYM
    
    FLUSH ::= FLUSH_SYM
    
    TBLLOCK_STMT ::= TABLELOCK  ID_LIST  SEMICOLON_SYM
    
    TABLELOCK ::= TABLELOCK_SYM
    
    ID_LIST ::= STD_ID
            ::= ID_LIST  LIST_SEP_SYM  STD_ID
    
    MOVE_REC_STMT ::= NEXT_SYM  TABLE  SEMICOLON_SYM
    
    CHANGE_STMT ::= CHANGE_HEADER  STATEMENT
    
    CHANGE_HEADER ::= CHANGE  LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM
    
    CHANGE ::= CHANGECOMP_SYM
           ::= CHANGESITE_SYM
    
    UNCHECKED_STMT ::= UNCHECKED_HEADER  STATEMENT
    
    UNCHECKED_HEADER ::= UNCHECKED_SYM  LEFT_PAR_SYM  IF_EXPR  RGHT_PAR_SYM

## See also

[X++ Syntax](x-syntax.md)

[X++ Keywords](x-keywords.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

