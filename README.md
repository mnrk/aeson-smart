# Aeson-smart

Better template haskell generation of parseJSON and toJSON methods

#### Sample usage:

    {-# LANGUAGE OverloadedStrings, TemplateHaskell #-}

    import Data.Aeson (FromJSON(..), decode)
    import Data.Aeson.TH.Smart (deriveFromJSON)

    data Person = Person { firstName  :: String
                         , middleName :: MaybeString
                         , lastName   :: String
                         , age        :: Integer }

    deriveFromJSON id True ''MyConfig

    fromJSON :: String -> Maybe Person
    fromJSON = decode . fromString
