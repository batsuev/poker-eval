cmake_minimum_required(VERSION 3.2)
project(poker_eval)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES
    include/inlines/eval.h
    include/inlines/eval_astud.h
    include/inlines/eval_joker.h
    include/inlines/eval_joker_low.h
    include/inlines/eval_joker_low8.h
    include/inlines/eval_low.h
    include/inlines/eval_low27.h
    include/inlines/eval_low8.h
    include/inlines/eval_omaha.h
    include/inlines/eval_type.h
    include/inlines/evx5.h
    include/inlines/evx7.h
    include/inlines/evx_action.h
    include/inlines/evx_inlines.h
    include/combinations.h
    include/config.h
    include/deck.h
    include/deck_astud.h
    include/deck_joker.h
    include/deck_std.h
    include/deck_undef.h
    include/enumdefs.h
    include/enumerate.h
    include/enumord.h
    include/evx_defs.h
    include/game_astud.h
    include/game_joker.h
    include/game_std.h
    include/handval.h
    include/handval_low.h
    include/md5c.h
    include/poker_config.h
    include/poker_defs.h
    include/poker_wrapper.h
    include/pokereval_export.h
    include/rules_astud.h
    include/rules_joker.h
    include/rules_std.h
    include/rules_undef.h
    lib/combinations.c
    lib/deck.c
    lib/deck_astud.c
    lib/deck_joker.c
    lib/deck_std.c
    lib/enumerate.c
    lib/enumord.c
    lib/lowball.c
    lib/poker_wrapper.c
    lib/rules_astud.c
    lib/rules_joker.c
    lib/rules_std.c
    lib/generated/t_astudcardmasks.c
    lib/generated/t_botcard.c
    lib/generated/t_botfivecards.c
    lib/generated/t_botfivecardsj.c
    lib/generated/t_cardmasks.c
    lib/generated/t_evx_flushcards.c
    lib/generated/t_evx_pairval.c
    lib/generated/t_evx_strval.c
    lib/generated/t_evx_tripsval.c
    lib/generated/t_jokercardmasks.c
    lib/generated/t_jokerstraight.c
    lib/generated/t_maskrank.c
    lib/generated/t_nbits.c
    lib/generated/t_nbitsandstr.c
    lib/generated/t_straight.c
    lib/generated/t_topbit.c
    lib/generated/t_topcard.c
    lib/generated/t_topfivebits.c
    lib/generated/t_topfivecards.c
    lib/generated/t_toptwobits.c)

include_directories(include/)
add_executable(hcmpn ${SOURCE_FILES} examples/hcmpn.c)
add_executable(pokenum ${SOURCE_FILES} examples/pokenum.c)
set_target_properties(hcmpn PROPERTIES COMPILE_FLAGS -DCARDS_DEALT=5)
