- {{cards [[模型分析]] }}
  template:: 每日复习
- #+BEGIN_QUERY
   {:title "⚠️ 到期任务"
    :query [:find (pull ?b [*])
            :in $ ?start ?today
            :where
            (task ?b #{"NOW" "LATER" "TODO" "DOING"})
            (between ?b ?start ?today)]
    :inputs [:-1y :-1d]
    :collapsed? false}
  #+END_QUERY
-
-