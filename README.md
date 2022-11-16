config icap profile
    edit "default"
    next
    edit "Demo"
        set response enable
        set streaming-content-bypass enable
        set preview enable
        set response-server "Trend-ICAP"
        set response-failure bypass
        set response-path "interscan"
        set methods get
        set respmod-default-action bypass
        config respmod-forward-rules
            edit "Status-200"
                set host "all"
                set http-resp-status-code 200
            next
        end
    next
end